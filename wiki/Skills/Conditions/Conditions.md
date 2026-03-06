# 条件 (Conditions)

条件は、スキルが発動するための条件を指定します。

---

## 概要

```yaml
Skills:
- <スキル> ?<条件>[{オプション}]    # 肯定条件（条件を満たす時に発動）
- <スキル> !<条件>[{オプション}]    # 否定条件（条件を満たさない時に発動）
```

複数の条件を組み合わせることも可能です：

```yaml
Skills:
- damage{a=10} @target ~onTimer:100 ?health{ph=50} ?onFire
```

---

## 条件の種類

### 体力・ダメージ系

| 条件 | 説明 |
|------|------|
| `health{ph=<パーセント>}` | 現在体力が指定パーセント以下 |
| `healthAbove{ph=<パーセント>}` | 現在体力が指定パーセント以上 |
| `lastDamageCause{cause=<ダメージタイプ>}` | 最後のダメージ原因が一致 |

### ターゲット系

| 条件 | 説明 |
|------|------|
| `hasTarget` | ターゲットが存在する |
| `targetInRange{r=<距離>}` | ターゲットが指定距離内にいる |
| `targetNotInRange{r=<距離>}` | ターゲットが指定距離外にいる |
| `targetIsPlayer` | ターゲットがプレイヤー |
| `targetIsMythicMob` | ターゲットが MythicMobs モブ |

### プレイヤー・ワールド系

| 条件 | 説明 |
|------|------|
| `inBiome{b=<バイオーム>}` | 指定バイオームにいる |
| `isInBlock{m=<ブロック>}` | 指定ブロックの中にいる |
| `onGround` | 地面に立っている |
| `isFlying` | 飛行中 |
| `isSwimming` | 水泳中 |
| `isSprinting` | 走っている |
| `isSneaking` | しゃがんでいる |
| `isBlocking` | ブロッキング中 |

### 時間・環境系

| 条件 | 説明 |
|------|------|
| `worldTime{min=<時間>;max=<時間>}` | ワールドの時刻が範囲内 |
| `isDay` | 昼間 |
| `isNight` | 夜間 |
| `isRaining` | 雨が降っている |
| `isThundering` | 雷雨が降っている |

### ポーション効果系

| 条件 | 説明 |
|------|------|
| `hasEffect{e=<効果名>}` | 指定のポーション効果を持っている |
| `onFire` | 炎上中 |

### レベル・スコア系

| 条件 | 説明 |
|------|------|
| `level{min=<レベル>;max=<レベル>}` | レベルが範囲内 |
| `score{o=<オブジェクティブ>;min=<値>;max=<値>}` | スコアボードの値が範囲内 |

### クールダウン系

| 条件 | 説明 |
|------|------|
| `onCooldown{s=<スキル名>}` | 指定スキルがクールダウン中 |
| `notOnCooldown{s=<スキル名>}` | 指定スキルがクールダウン中でない |

### 乱数系

| 条件 | 説明 |
|------|------|
| `chance{c=<確率>}` | 指定確率（0.0〜1.0）でランダムに発動 |

---

## 使用例

```yaml
PhaseShifter:
  Type: ENDER_DRAGON
  Skills:
  # HP50%以下でフェーズ2に移行
  - skill{s=Phase2Entry} ~onHealthBelow:50

  # HP50%以下かつ昼間のみに使用するスキル
  - skill{s=SunWeaknessSkill} ~onTimer:100 ?health{ph=50} ?isDay

  # ターゲットが10ブロック以内の場合に近接攻撃
  - damage{a=20} @target ~onTimer:40 ?targetInRange{r=10}

  # ターゲットが遠い場合にファイアボール
  - projectile{...} @target ~onTimer:60 ?targetNotInRange{r=10}

  # 10% の確率で追加ダメージ
  - damage{a=50} @target ~onAttack ?chance{c=0.1}

  # 夜間のみ使用する闇のスキル
  - skill{s=DarkPower} ~onTimer:80 ?isNight

  # 炎上中でない時のみ使用
  - skill{s=FireSkill} ~onTimer:100 !onFire
```

---

## 複数条件の組み合わせ

```yaml
Skills:
# HP25%以下かつターゲットが近い場合のみ発動
- skill{s=BerserkMode} ~onTimer:100 ?health{ph=25} ?targetInRange{r=5}
```

---

[← スキルに戻る](../Skills.md) | [← ホームに戻る](../../Home.md)
