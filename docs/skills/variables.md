# 変数 (Variables)

変数は情報を保存するためのシステムです。変数システムを使用することで、後でプレースホルダーや条件で使用できる値を保存・操作できます。これらの値は永続的または一時的に設定できます。

## 変数タイプ

変数は[setVariable](mechanics/setvariable.md)メカニクスを使用して変数を初期化するときに定義されるいくつかのタイプのいずれかを取ることができます。

| タイプ | 説明 |
|------|------|
| INTEGER | 小数点なしの数値 |
| FLOAT | 小数点ありの数値 |
| LONG | 小数点なしの数値。INTよりも大きな数値を表現できます |
| DOUBLE | 小数点ありの数値。FLOATよりも大きな数値を表現できます |
| STRING | 単語または文章 |
| BOOLEAN | true または false の値 |
| SET | 順序付けられていないユニークな値のセット |
| LIST | エントリの順序付きリスト |
| MAP | キーと値のペアのリスト |
| LOCATION | サーバー上の場所 |
| VECTOR | 3つのDOUBLE値で構成されるリスト |
| TIME | エポックからのミリ秒数で表される時点 |
| METASKILL | インラインメタスキル |
| ITEM | アイテムのデータを保存・変更するためのアイテムスタック |

## 変数スコープ

変数の「スコープ」は、その変数が**どこに**存在するかを示します。

| スコープ | 変数の存在場所 |
|---------|-------------|
| SKILL | 現在のスキルツリー上。常に一時的で、スキルのキューが終了すると消えます |
| CASTER | キャスティングモブ上 |
| TARGET | メカニクス/コンディションのターゲット上 |
| WORLD | 現在のワールド |
| GLOBAL | サーバー |

## 使用方法

すべての変数メカニクスとコンディションは、作業したい変数とその場所を決定するために`var=`と`scope=`属性を受け付けます。

```yaml
- setvariable{var=target.somevariable; ...}
- setvariable{var=somevariable;scope=target; ...}
```

> 変数名にはドット(`.`)文字を含めないでください！区切り文字として使用されており、変数名に含めると予期しない動作が発生します！

## 変数タイプの動作

### 数値変数

```yaml
# 数値変数を作成
- setvariable{var=skill.example;type=DOUBLE;val=1.5}

# 値を追加
- variableadd{var=skill.example;amount=2}

# 値を減算
- variablesubtract{var=skill.example;amount=1}

# 数値を出力
- message{m=<skill.var.example>} # 2.5
```

### 文字列変数

```yaml
# 文字列変数を作成
- setvariable{var=skill.example;type=STRING;val="こんにちは"}

# 文字列に追加
- variableadd{var=skill.example;amount=" 世界"}

# 文字列を出力
- message{m=<skill.var.example>} # こんにちは 世界
```

### ブール変数

```yaml
# ブール変数を作成
- setvariable{var=skill.example;type=BOOLEAN;val=true}

# ブールを出力
- message{m=<skill.var.example>} # true
```

### リスト変数

```yaml
# リストを作成
- setvariable{var=skill.example;type=LIST;val=1,2,hello}

# リストに値を追加
- variableadd{var=skill.example;amount=world}

# インデックスでリストから値を削除
- variablesubtract{var=skill.example;amount=0}

# リストを出力
- message{m=<skill.var.example>} # 2,hello,world
- message{m=<skill.var.example.0>} # 2
```

### マップ変数

```yaml
# マップを作成
- setvariable{var=skill.example;type=MAP;val="hello=world;mamma=mia"}

# マップに値を追加
- variableadd{var=skill.example;amount="pizza=pasta"}

# キーでマップから値を削除
- variablesubtract{var=skill.example;amount=hello}

# マップを出力
- message{m=<skill.var.example>} # mamma=mia;pizza=pasta
- message{m=<skill.var.example.pizza>} # pasta
```

### 場所変数

```yaml
# 場所変数を作成
- setvariable{var=skill.example;type=LOCATION;val=world,1,2,3}
- setvarloc{var=skill.specialexample;val=@selflocation}

# 座標値を増加
- variableadd{var=skill.example;amount=1,2,3}

# 場所を出力
- message{m=<skill.var.example>} # world,1.0,3.0,5.0
```

## 実践的な例

### カウンターの実装

```yaml
KillCounter:
  Skills:
  - setvariable{var=caster.kills;type=INTEGER;val=<caster.var.kills + 1>} @self ~onPlayerKill
  - message{m="倒したプレイヤー数: <caster.var.kills>"} @self ~onPlayerKill
```

### フラグの使用

```yaml
BossPhaseSkill:
  Conditions:
  - variableequals{var=caster.phase2;type=BOOLEAN;value=false} true
  Skills:
  - setvariable{var=caster.phase2;type=BOOLEAN;val=true} @self
  - message{m="第2フェーズ開始！"} @PlayersInRadius{r=50}
```
