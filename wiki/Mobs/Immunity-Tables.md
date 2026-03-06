# 免疫テーブル (Immunity Tables)

MythicMobs の免疫システムにより、特定のポーション効果やダメージ源に対する耐性を設定できます。

---

## 概要

デフォルトでは、MythicMobs のモブはバニラの免疫設定に従います。免疫テーブルを使うと、モブが免疫を持つ効果を細かく制御できます。

---

## 基本構文

```yaml
MobName:
  Immunities:
  - lightning
  - fall
  - drowning
  - void
  - fire
  - SLOW
  - POISON
```

---

## 免疫の種類

### ダメージタイプへの免疫

| 免疫 | 説明 |
|------|------|
| `lightning` | 落雷ダメージへの免疫 |
| `fall` | 落下ダメージへの免疫 |
| `drowning` | 溺死への免疫 |
| `void` | 奈落への免疫 |
| `fire` | 炎へのダメージ免疫 |
| `lava` | 溶岩ダメージへの免疫 |
| `contact` | 接触ダメージへの免疫 |
| `suffocation` | 窒息への免疫 |
| `wither` | ウィザー効果への免疫 |
| `poison` | 毒ダメージへの免疫 |
| `starvation` | 飢えへの免疫 |
| `cramming` | モブ圧縮への免疫 |
| `freeze` | 凍結への免疫 |

### ポーション効果への免疫

ポーション効果の名前（大文字）を使用します：

| 免疫 | 説明 |
|------|------|
| `SLOW` | 鈍化への免疫 |
| `SLOW_DIGGING` | 採掘速度低下への免疫 |
| `FAST_DIGGING` | ← これは効果ではなく速度上昇のため不要 |
| `INCREASE_DAMAGE` | 筋力への免疫 |
| `HEAL` | 即時回復への免疫 |
| `HARM` | 即時ダメージへの免疫 |
| `JUMP` | ジャンプ強化への免疫 |
| `CONFUSION` | 吐き気への免疫 |
| `REGENERATION` | 再生への免疫 |
| `DAMAGE_RESISTANCE` | ダメージ耐性への免疫 |
| `FIRE_RESISTANCE` | 耐火への免疫 |
| `WATER_BREATHING` | 水中呼吸への免疫 |
| `INVISIBILITY` | 透明化への免疫 |
| `BLINDNESS` | 盲目への免疫 |
| `NIGHT_VISION` | 暗視への免疫 |
| `HUNGER` | 空腹への免疫 |
| `WEAKNESS` | 弱体化への免疫 |
| `POISON` | 毒への免疫 |
| `WITHER` | ウィザー効果への免疫 |
| `HEALTH_BOOST` | 体力増強への免疫 |
| `ABSORPTION` | 吸収への免疫 |
| `SATURATION` | 満腹への免疫 |
| `GLOWING` | 発光への免疫 |
| `LEVITATION` | 浮遊への免疫 |
| `LUCK` | 幸運への免疫 |
| `UNLUCK` | 不運への免疫 |
| `SLOW_FALLING` | 落下速度低下への免疫 |
| `CONDUIT_POWER` | コンジットパワーへの免疫 |
| `DOLPHINS_GRACE` | イルカの恩恵への免疫 |
| `BAD_OMEN` | 不吉な予感への免疫 |
| `HERO_OF_THE_VILLAGE` | 村の英雄への免疫 |
| `DARKNESS` | 暗闇への免疫 |

---

## 設定例

```yaml
# 炎と水の完全耐性を持つゴーレム
LavaGolem:
  Type: MAGMA_CUBE
  Display: "&c&lラヴァゴーレム"
  Health: 300
  Immunities:
  - fire
  - lava
  - drowning
  - FIRE_RESISTANCE

# 魔法耐性を持つウィッチハンター
WitchHunter:
  Type: SKELETON
  Display: "&7ウィッチハンター"
  Health: 150
  Immunities:
  - POISON
  - SLOW
  - WEAKNESS
  - BLINDNESS
  - CONFUSION
```

---

## 注意事項

- ダメージタイプの免疫は小文字で記述します。
- ポーション効果の免疫は大文字で記述します。
- 一部の免疫はバニラのエンティティが既に持っている場合があります（例：ゾンビの溺死耐性）。

---

[← モブ設定に戻る](Mobs.md) | [← ホームに戻る](../Home.md)
