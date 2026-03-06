# ダメージ修正値 (Damage Modifiers)

MythicMobs では、特定のダメージタイプに対するダメージの倍率を設定できます。

---

## 概要

`DamageModifiers` を使うと、モブが受けるダメージタイプごとに倍率を設定できます。例えば、火に強いモブや、矢に弱いモブなどを作成できます。

---

## 基本構文

```yaml
MobName:
  Type: ZOMBIE
  DamageModifiers:
  - FIRE 0.0           # 火ダメージを無効化
  - ARROW 2.0          # 矢ダメージを2倍に
  - ENTITY_ATTACK 0.5  # 近接ダメージを半減
```

---

## ダメージタイプ一覧

| ダメージタイプ | 説明 |
|--------------|------|
| `CONTACT` | 接触（サボテンなど） |
| `ENTITY_ATTACK` | エンティティによる近接攻撃 |
| `ENTITY_SWEEP_ATTACK` | スイープ攻撃 |
| `PROJECTILE` | 発射物（矢など） |
| `SUFFOCATION` | 窒息 |
| `FALL` | 落下ダメージ |
| `FIRE` | 炎による持続ダメージ |
| `FIRE_TICK` | 炎上による持続ダメージ |
| `MELTING` | 雪だるまが溶けるダメージ |
| `LAVA` | 溶岩 |
| `DROWNING` | 溺死 |
| `BLOCK_EXPLOSION` | ブロックの爆発（TNTなど） |
| `ENTITY_EXPLOSION` | エンティティの爆発（クリーパーなど） |
| `VOID` | 奈落 |
| `LIGHTNING` | 雷撃 |
| `SUICIDE` | 自殺コマンド |
| `STARVATION` | 飢え |
| `POISON` | 毒 |
| `MAGIC` | 魔法（スプラッシュポーション等） |
| `WITHER` | ウィザー効果 |
| `FALLING_BLOCK` | 落下するブロック |
| `THORNS` | 棘の鎧 |
| `DRAGON_BREATH` | ドラゴンブレス |
| `CUSTOM` | カスタムダメージ |
| `FLY_INTO_WALL` | 壁への衝突 |
| `HOT_FLOOR` | 灼熱の地面（マグマブロック等） |
| `CRAMMING` | モブ圧縮ダメージ |
| `DRYOUT` | 乾燥（ドルフィン等） |
| `FREEZE` | 凍結（粉雪など） |
| `ARROW` | 矢（特定プラグイン向け） |
| `TRIDENT` | トライデント |
| `SONIC_BOOM` | ウォーデンの音波攻撃 |

---

## 倍率の意味

| 倍率 | 効果 |
|------|------|
| `0.0` | ダメージ無効（完全耐性） |
| `0.5` | ダメージ半減 |
| `1.0` | 通常のダメージ（デフォルト） |
| `2.0` | 2倍のダメージ（弱点） |

---

## 設定例

```yaml
FireResistantGolem:
  Type: IRON_GOLEM
  Display: "&c&l炎の傀儡"
  Health: 500
  DamageModifiers:
  - FIRE 0.0           # 炎ダメージ無効
  - FIRE_TICK 0.0      # 炎上ダメージ無効
  - LAVA 0.0           # 溶岩ダメージ無効
  - PROJECTILE 0.5     # 発射物ダメージ半減
  - ENTITY_ATTACK 0.75 # 近接攻撃ダメージ25%減

IceSkeleton:
  Type: SKELETON
  Display: "&b&l氷のスケルトン"
  Health: 100
  DamageModifiers:
  - FIRE 2.0           # 炎に弱い
  - LAVA 2.0           # 溶岩に弱い
  - FREEZE 0.0         # 凍結ダメージ無効
  - ARROW 0.5          # 矢に耐性
```

---

[← モブ設定に戻る](Mobs.md) | [← ホームに戻る](../Home.md)
