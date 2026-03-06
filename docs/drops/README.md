# ドロップ (Drops)

Dropsタグをカスタムモブに追加することで、死亡時に選択したアイテムをドロップさせることができます。MythicMobsには3種類のカスタムドロップがあります。

## ドロップ設定

```yaml
internal_mobname:
  Type: <mobtype>
  Drops:
  - <drop> <amount> <chance>
  - <drop> <amount> <chance>
  - ...
```

### ドロップ（Drop）

MythicMobsアイテム、バニラアイテム、経験値、ドロップテーブル、またはサポートされているプラグインのアイテム/経験値を指定できます。

### 数量（Amount）

ドロップするアイテムの数量。数量範囲（例：`1-3`または`1to3`）を使用できます。

### 確率（Chance）

指定されたアイテムがドロップする確率。
- 0から1の間の数値が必要
- パーセンテージ確率が使用可能（0.1の代わりに10%）

## ドロップタイプ

| タイプ | 説明 | 例 |
|------|------|-----|
| [MythicMob](drop-types/mythicmob.md) | MythicMobをドロップします | |
| [Mythic Item](drop-types/mythicitem.md) | Mythicアイテムをドロップします | |
| [VanillaLootTable](drop-types/vanillaLoottable.md) | バニラのルートテーブルからアイテムをドロップします | `- vanillaLootTable minecraft:table_name` |
| **champions-exp** | Championsプラグインの経験値をドロップします | |
| **skillapi-exp** | SkillAPIプラグインの経験値をドロップします | |
| **heroesexp** | Heroesプラグインの経験値をドロップします | |
| **mcmmo-exp** | MCMMOプラグインの経験値をドロップします | `- mcmmo-exp 69` |
| **exp** | 通常のMinecraft経験値をドロップします | `- exp 420` |
| [money](drop-types/money.md) | Vaultプラグインのお金をドロップします | `- money 1500` |
| **mythicdrop** | MythicDropsプラグインのアイテムをドロップします | `- mythicdrop CoolSword 1` |
| **phatloot** | PhatLootプラグインのアイテムをドロップします | `- phatloot LootTableName 1` |
| [command](drop-types/command.md) | コンソールでコマンドを実行します | `- cmd{c="warp <trigger.name> spawn"} 1` |
| **nothing** | 何もドロップしません（重み付きドロップテーブルの作成に便利） | `- nothing` |
| [ItemVariable](drop-types/itemvariable.md) | 指定されたアイテム変数で定義されたアイテムをドロップします | `- itemvariable{variable=caster.stolenitem} 1 1` |

### 例

この例では、20%の確率でダイヤモンド3個、60%の確率でコマンドを実行、12%の確率で100から600の経験値をドロップします。

```yaml
YourMob:
  Type: ZOMBIE
  Drops:
  - diamond 3 0.2
  - cmd{c="crate give <trigger.name> RewardCrate 1"} 1 0.6
  - exp 100to600 0.12
```

## インラインドロップ

基本的な装備の場合、Mythicアイテムを常に作成しなくても済むように、インラインアイテムデータを追加できます。

```yaml
Drops:
- leather_chestplate{name="ダークレザー";lore="&8黒ずんだ革で作られたベスト";color=BLACK} 1 1
```

## ドロップテーブル (DropTables)

ドロップテーブルを使うと、複数のモブで同じドロップ設定を再利用できます。
[ドロップテーブル](drop-tables.md)を参照してください。

## サブページ

- [ドロップテーブル](drop-tables.md)
- [ドロップタイプ](drop-types.md)
- [ファンシードロップ](fancy-drops.md)
