# スキル (Skills)

MythicMobs のスキルシステムは、モブの行動パターンや特殊能力を定義するための中核機能です。

---

## 概要

スキルは以下の要素で構成されます：

1. **メカニクス (Mechanics)**: 実際に実行される動作（ダメージ、テレポート、エフェクトなど）
2. **トリガー (Triggers)**: スキルが発動するタイミング
3. **ターゲット (Targeters)**: スキルの対象
4. **条件 (Conditions)**: スキル発動の条件

---

## スキルの定義方法

### インラインスキル（モブ定義内に直接書く）

```yaml
MobName:
  Skills:
  - mechanic{option=value} @target ~onTimer:100 =condition 0.5
```

形式：`<メカニクス> [@ターゲット] [~トリガー] [=条件] [確率]`

### 外部スキルファイルの参照

`plugins/MythicMobs/Skills/` フォルダに別ファイルとしてスキルを定義できます：

```yaml
# Skills/MySkills.yml

FireballSkill:
  Skills:
  - projectile{...} @target
  - effect:particles{...} @self
```

モブから参照する場合：

```yaml
MobName:
  Skills:
  - skill{s=FireballSkill} ~onTimer:100
```

---

## スキルの基本構文

```yaml
Skills:
- <メカニクス>{<オプション>} @<ターゲット> ~<トリガー>:<値> ?<条件> <確率>
```

| 要素 | 説明 |
|------|------|
| `メカニクス{...}` | 実行する動作と設定 |
| `@ターゲット` | 動作対象の指定 |
| `~トリガー` | 発動タイミング |
| `?条件` | 発動条件 |
| `確率` | 発動確率（0.0〜1.0） |

---

## スキルの例

```yaml
DarkMage:
  Type: WITCH
  Skills:
  # 100tick（5秒）ごとに近接ターゲットにダメージ
  - damage{a=10} @NearestPlayer{r=5} ~onTimer:100

  # 死亡時に爆発エフェクト
  - effect:explosion @self ~onDeath

  # 体力が50%以下になったらファイアボールを発射
  - projectile{onTick=SkillOnTick;onHit=SkillOnHit} @target ~onTimer:60 ?health{ph=50}

  # 外部スキルファイルのスキルを使用
  - skill{s=DarkMageUltraSkill} ~onTimer:200 0.5
```

---

## トリガー (Triggers)

スキルが発動するタイミングを設定します。

| トリガー | 説明 |
|---------|------|
| `~onTimer:<tick数>` | 指定 tick ごとに発動（20tick = 1秒） |
| `~onSpawn` | スポーン時に発動 |
| `~onDeath` | 死亡時に発動 |
| `~onDamaged` | ダメージを受けた時に発動 |
| `~onAttack` | 攻撃した時に発動 |
| `~onKillPlayer` | プレイヤーを倒した時に発動 |
| `~onCombat` | 戦闘開始時に発動 |
| `~onChangeTarget` | ターゲットが変わった時に発動 |
| `~onReady` | 準備完了時（スポーン後少し経ってから）に発動 |
| `~onEnterCombat` | 戦闘に入った時に発動 |
| `~onLeaveCombat` | 戦闘を離れた時に発動 |
| `~onHealthBelow:<パーセント>` | 体力が指定パーセント以下になった時に発動 |

詳細は [トリガー](Triggers.md) を参照してください。

---

## ターゲット (Targeters)

スキルの対象を指定します。

| ターゲット | 説明 |
|-----------|------|
| `@self` | 自分自身 |
| `@target` | 現在のターゲット |
| `@NearestPlayer{r=<半径>}` | 最も近いプレイヤー |
| `@PlayersInRadius{r=<半径>}` | 範囲内のプレイヤー |
| `@Location{x=<X>;y=<Y>;z=<Z>}` | 特定の座標 |
| `@forward{d=<距離>}` | 前方の座標 |

詳細は [ターゲット](Targeters/Targeters.md) を参照してください。

---

## 条件 (Conditions)

スキルが発動する条件を設定します。`?` が肯定条件、`!` が否定条件です。

```yaml
Skills:
- damage{a=10} @target ~onTimer:100 ?health{ph=50}   # HP50%以下の時のみ
- damage{a=5} @target ~onTimer:100 !health{ph=50}    # HP50%より高い時のみ
- skill{s=X} ~onTimer:100 ?onCooldown{s=X;cd=200}    # クールダウン中でない時のみ
```

詳細は [条件](Conditions/Conditions.md) を参照してください。

---

## スキルの確率

スキルの末尾に数値（0.0〜1.0）を指定すると、その確率でスキルが発動します：

```yaml
Skills:
- damage{a=10} @target ~onTimer:100 1.0    # 100% の確率（デフォルト）
- fireball @target ~onTimer:100 0.5         # 50% の確率
- effect:explosion @self ~onDeath 0.1       # 10% の確率
```

---

## 外部スキルファイルの構造

```yaml
# plugins/MythicMobs/Skills/BossSkills.yml

UltraFireball:
  Cooldown: 10
  Skills:
  - effect:particles{p=FLAME;a=20;hs=0.5} @self
  - projectile{v=3;onHit=UltraFireballHit} @forward{d=1}

UltraFireballHit:
  Skills:
  - damage{a=20} @EntitiesInRadius{r=3}
  - effect:explosion @self
  - effect:particles{p=EXPLOSION_LARGE;a=5} @self
```

---

## 関連ページ

- [トリガー (Triggers)](Triggers.md)
- [ターゲット (Targeters)](Targeters/Targeters.md)
- [条件 (Conditions)](Conditions/Conditions.md)
- [メカニクス (Mechanics)](Mechanics/Mechanics.md)
- [エフェクト (Effects)](Effects.md)

---

[← ホームに戻る](../Home.md)
