# Command（コマンド実行）

## 説明

各ターゲットに対してコマンドを実行します。

[カラーコード](/Skills/Placeholders#color-codes)と[変数](/Skills/Variables)が使用可能です。

コマンドの中にダブルクォーテーション `"` や波括弧 `{}` を含めることはできません。それぞれ対応する[メッセージ変数](/skills/Placeholders#special-characters)に置き換える必要があります。  
これは、MythicMobs がその構文を読み取るためにダブルクォーテーションと波括弧を予約しているためです。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| command | c, cmd | 実行するコマンド | |
| asCaster | ac, caster, sudo, asmob | trueの場合、コンソールではなくキャスター（術者）としてコマンドを実行する | false |
| asOp | op | すべての権限でコマンドを実行するか | false |
| asTarget | at, target, sudotarget | ターゲットエンティティとしてコマンドを実行する | false |
| requireTarget | rt | スキルにターゲットがある場合のみ実行する | asTarget の値 |

## 使用例

### 正しいコマンドスキルの例
```yaml
  Skills:
  - command{c="give <target.name> gold_ingot 20"} @trigger ~onInteract
  - command{c="minecraft:tp <target.name> <mob.uuid>"} @self ~onDamaged
  - command{c="say HELLO <target.name>";asTarget=true;asOp=true} @NearestPlayer{r=10}
```

### 無効なコマンドスキルの例

以下の例は特定の記号が置換されていないため動作しません:
```yaml
  Skills:
  - command{c="minecraft:summon Zombie ~ ~ ~ {NoAI:true,CustomName:"Summoned Zombie"}"}
```
> この例では `~` シンボルが問題です。コンソールとして実行する場合は「位置」が存在しないため使用できません。代わりに `<caster.l.x>`・`<caster.l.y>`・`<caster.l.z>` プレースホルダーを使用してください。

### プレイヤーにコマンドを実行させる例
```yaml
ExampleMob:
  Type: ZOMBIE
  Skills:
  - command{c="say <target.name>";asTarget=true;asOp=true} @trigger ~onInteract
```

## エイリアス
- [x] cmd
