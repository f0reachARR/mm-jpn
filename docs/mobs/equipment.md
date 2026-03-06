# 装備 (Equipment)

モブ設定のEquipmentセクションは、モブがスポーン時にどのような装備を持つかを定義します。装備はモブがスポーンするとき、またはリロード中にのみ適用され、その後は[Equipメカニクス](../skills/mechanics/equip.md)を使用して変更できます。

`PreventOtherDrops`オプションが有効になっていない場合、モブは死亡時にすべての装備アイテムを自然にドロップします。

モブに装備を着用させたくない場合は、`PreventRandomEquipment`オプションを使用できます。

## 構文

```yaml
internal_mobname:
  Type: <mobtype>
  Equipment:
  - <item> <slot>
  - <item> <slot>
  - ...
```

### アイテム（Item）

[MythicMobsアイテム](../items/README.md)の名前またはバニラアイテムを使用できます。

### スロット（Slot）

モブがアイテムを持つスロットを定義します。

| スロット | 説明 |
|--------|------|
| HEAD | 頭スロット。通常のヘルメット、プレイヤーヘッド、ブロックタイプも使用可能 |
| CHEST | 胸スロット。チェストプレートのみ表示されますが、どのアイテムも持てます |
| LEGS | 脚スロット。レギンスのみ表示されますが、どのアイテムも持てます |
| FEET | 足スロット。ブーツのみ表示されますが、どのアイテムも持てます |
| HAND | メインハンド（右）スロット |
| OFFHAND | オフハンド（左）スロット |

```yaml
awesome_boss:
  Type: pig_zombie
  Equipment:
  - awesome_boss_helmet HEAD
  - diamond_sword HAND
```

## インラインアイテム

非常に基本的な装備の場合、Mythicアイテムを常に作成しなくても済むように、インラインアイテムデータを追加できます。

```yaml
Equipment:
- leather_chestplate{name="ダークレザー";lore="&8黒ずんだ革で作られたベスト";color=BLACK} CHEST
```

### 利用可能なインライン属性

| 属性 | エイリアス | 説明 | デフォルト |
|-----|---------|------|---------|
| name | display, n, d | アイテムの表示名 | |
| data | | アイテムのデータ | 0 |
| model | | アイテムのCustomModelData | 0 |
| amount | a | アイテムの数量 | 1 |
| lore | l | アイテムの説明文 | |
| enchantments | enchants, ench, e | アイテムのエンチャントリスト | |
| color | c | アイテムの色（ポーションの場合） | |
| skullowner | | スカルのオーナー | |
| skulltexture | | スカルのスキンURL | |

## MMOItemsの装備

```yaml
Equipment:
- mmoitems{type=ARMOR;id=STEEL_HELMET} HEAD
- mmoitems{type=ARMOR;id=STEEL_CHESTPLATE} CHEST
```

## 例

```yaml
PandaZombie:
  Type: ZOMBIE
  Options:
    PreventSunburn: true
  Equipment:
  - PLAYER_HEAD{skullTexture=eyJ0ZXh0dXJlcyI6...} HEAD
  - DIAMOND_CHESTPLATE{name="パンダの意志";lore="パンダは警戒しなければならない";enchants=PROTECTION_ENVIRONMENTAL:4,MENDING:1} CHEST
  - DIAMOND_LEGGINGS{name="パンダの強さ";lore="パンダは強くなければならない"} LEGS
  - DIAMOND_BOOTS{name="パンダの速さ";lore="パンダは速くなければならない"} FEET
```
