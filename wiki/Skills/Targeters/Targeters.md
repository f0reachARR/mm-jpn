# ターゲット (Targeters)

ターゲットは、スキルの効果を適用する対象を指定します。

---

## 概要

```yaml
Skills:
- <メカニクス> @<ターゲット>[{オプション}]
```

ターゲットは `@` から始まります。オプションはセミコロン（`;`）区切りで指定します。

---

## エンティティターゲット

### 自分自身

| ターゲット | 説明 |
|-----------|------|
| `@self` | スキルを使用したモブ自身 |
| `@Self` | 同上（大文字小文字どちらでも可） |

### プレイヤーターゲット

| ターゲット | 説明 |
|-----------|------|
| `@target` | 現在のターゲット（主ターゲット） |
| `@Target` | 同上 |
| `@NearestPlayer` | 最も近くにいるプレイヤー1名 |
| `@RandomPlayer` | ランダムな1名のプレイヤー |
| `@PlayersInRadius{r=<半径>}` | 指定半径内の全プレイヤー |
| `@PlayersInWorld` | 同ワールドの全プレイヤー |
| `@PlayersOnServer` | サーバー上の全プレイヤー |

### エンティティターゲット

| ターゲット | 説明 |
|-----------|------|
| `@EntitiesInRadius{r=<半径>}` | 指定半径内の全エンティティ |
| `@NearestEntity{r=<半径>}` | 最も近いエンティティ |
| `@MobsInRadius{r=<半径>}` | 指定半径内の全モブ |
| `@NearestMob{r=<半径>}` | 最も近いモブ |
| `@MythicMobsInRadius{r=<半径>}` | 指定半径内の全 MythicMobs モブ |

### 攻撃者ターゲット

| ターゲット | 説明 |
|-----------|------|
| `@trigger` | スキルを発動させたエンティティ（攻撃者など） |
| `@Trigger` | 同上 |

---

## 座標ターゲット

| ターゲット | 説明 |
|-----------|------|
| `@selfLocation` | 自分自身の座標 |
| `@SelfLocation` | 同上 |
| `@targetLocation` | ターゲットの座標 |
| `@forward{d=<距離>}` | 正面方向の指定距離先の座標 |
| `@Location{x=<X>;y=<Y>;z=<Z>}` | ワールドの絶対座標 |
| `@RelativeLocation{f=<前>;r=<右>;u=<上>}` | 相対座標 |
| `@SpawnLocation` | スポーン座標 |
| `@NearestStructure{...}` | 最も近い構造物の座標 |

---

## ターゲットオプション

### 共通オプション

| オプション | 説明 |
|-----------|------|
| `r=<数>` | 半径（ブロック） |
| `limit=<数>` | ターゲットの最大数 |
| `sort=NEAREST` / `sort=FURTHEST` / `sort=RANDOM` | ターゲットの並び順 |
| `tFilter=<フィルター>` | エンティティタイプフィルター |

### 例

```yaml
Skills:
# 半径10内の最大3人のプレイヤーをランダムに選択
- damage{a=10} @PlayersInRadius{r=10;limit=3;sort=RANDOM}

# 前方5ブロック先を中心にダメージ
- effect:explosion @forward{d=5}

# 半径5内のゾンビのみを対象
- damage{a=20} @MobsInRadius{r=5;tFilter=ZOMBIE}
```

---

## 複合ターゲット

複数のターゲットを組み合わせることはできませんが、スキルを複数行に分けることで対応できます：

```yaml
Skills:
- damage{a=10} @target ~onAttack          # ターゲットにダメージ
- effect:particles{p=FLAME;a=10} @self    # 自分にパーティクル
```

---

## 設定例

```yaml
AreaBoss:
  Type: BLAZE
  Skills:
  # 近くの全プレイヤーにダメージ（範囲攻撃）
  - damage{a=8} @PlayersInRadius{r=8} ~onTimer:60

  # 最も近いプレイヤーを追いかける方向にファイアボール発射
  - projectile{...} @NearestPlayer{r=20} ~onTimer:80

  # 自分自身を回復
  - heal{a=10} @self ~onTimer:100

  # 死亡時に周囲を爆発
  - effect:explosion{power=3} @selfLocation ~onDeath
```

---

## 関連ページ

- [スキルの概要](../Skills.md)
- [メカニクス](../Mechanics/Mechanics.md)
- [条件](../Conditions/Conditions.md)

---

[← スキルに戻る](../Skills.md) | [← ホームに戻る](../../Home.md)
