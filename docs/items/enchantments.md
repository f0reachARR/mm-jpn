# エンチャント (Enchantments)

MythicMobsアイテムには任意のエンチャントを付与できます。バニラのエンチャントとカスタムエンチャント（プラグインが必要）の両方をサポートしています。

## フォーマット

```yml
example_item:
  Id: diamond_sword
  Enchantments:
  - ENCHANTMENT_NAME:level
  - ENCHANTMENT_NAME:level
```

## バニラエンチャント一覧

### 武器エンチャント

| エンチャント | 説明 | 最大レベル |
|-----------|------|----------|
| DAMAGE_ALL (Sharpness) | 全ての攻撃に追加ダメージ | 5 |
| DAMAGE_UNDEAD (Smite) | アンデッドへの追加ダメージ | 5 |
| DAMAGE_ARTHROPODS (Bane of Arthropods) | 節足動物への追加ダメージ | 5 |
| KNOCKBACK | ノックバック距離を増加 | 2 |
| FIRE_ASPECT | 攻撃対象に火をつける | 2 |
| LOOT_BONUS_MOBS (Looting) | モブのドロップ増加 | 3 |
| SWEEPING_EDGE | スウィープ攻撃のダメージ増加 | 3 |

### 弓エンチャント

| エンチャント | 説明 | 最大レベル |
|-----------|------|----------|
| ARROW_DAMAGE (Power) | 矢のダメージ増加 | 5 |
| ARROW_KNOCKBACK (Punch) | 矢のノックバック増加 | 2 |
| ARROW_FIRE (Flame) | 矢に火をつける | 1 |
| ARROW_INFINITE (Infinity) | 矢を無限に使用 | 1 |

### ツールエンチャント

| エンチャント | 説明 | 最大レベル |
|-----------|------|----------|
| DIG_SPEED (Efficiency) | 採掘速度増加 | 5 |
| SILK_TOUCH | ブロックをそのままドロップ | 1 |
| LOOT_BONUS_BLOCKS (Fortune) | ブロックのドロップ増加 | 3 |

### 防具エンチャント

| エンチャント | 説明 | 最大レベル |
|-----------|------|----------|
| PROTECTION_ENVIRONMENTAL (Protection) | 全般的なダメージ軽減 | 4 |
| PROTECTION_FIRE (Fire Protection) | 火ダメージ軽減 | 4 |
| PROTECTION_FALL (Feather Falling) | 落下ダメージ軽減 | 4 |
| PROTECTION_EXPLOSIONS (Blast Protection) | 爆発ダメージ軽減 | 4 |
| PROTECTION_PROJECTILE (Projectile Protection) | 発射物ダメージ軽減 | 4 |
| THORNS | 攻撃者にダメージを与える | 3 |
| DEPTH_STRIDER | 水中移動速度増加 | 3 |
| FROST_WALKER | 水の上を歩ける | 2 |
| SOUL_SPEED | ソウルサンド/ソウルソイルでの移動速度増加 | 3 |

### ユニバーサルエンチャント

| エンチャント | 説明 | 最大レベル |
|-----------|------|----------|
| DURABILITY (Unbreaking) | 耐久力増加 | 3 |
| MENDING | 経験値でアイテムを修復 | 1 |
| VANISHING_CURSE | 死亡時にアイテムが消える | 1 |
| BINDING_CURSE | アイテムを取り外せなくする | 1 |

## 例

```yml
DragonSlayerSword:
  Id: NETHERITE_SWORD
  Display: '&4ドラゴンスレイヤー'
  Enchantments:
  - DAMAGE_ALL:5        # シャープネス5
  - FIRE_ASPECT:2       # ファイアアスペクト2
  - KNOCKBACK:2         # ノックバック2
  - DURABILITY:3        # アンブレイキング3
  - MENDING:1           # メンディング1
```
