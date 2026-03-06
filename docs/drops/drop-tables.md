# ドロップテーブル (Drop Tables)

ドロップテーブルは、モブに割り当てることができる複数のドロップのコレクションです。これを使用することで、モブが複数のアイテムをドロップする場合のドロップ整理が容易になります。

ドロップテーブルは`/MythicMobs/DropTables`フォルダにある専用の設定ファイルに保存されています。[コンディション](../skills/conditions.md)や様々な特別なオプションを使用する利点があり、複数のモブで複製せずに共有できます。

DropTablesフォルダに何個でもファイルを作成でき、ファイル名は`.yml`で終わる限り何でも構いません。

ドロップテーブルはネストできます（ドロップテーブルは複数の他のドロップテーブルを含むことができます）。

```yaml
internal_mobname:
  Type: <mobtype>
  Drops:
  - <internal_droptablename>
```

完全に設定されたドロップテーブルの構造は以下の通りです：

```yaml
internal_droptablename:
  TotalItems: <amount>
  MinItems: <amount>
  MaxItems: <amount>
  BonusLuckItems: <multiplier>
  BonusLevelItems: <multiplier>
  Conditions:
  - condition 1
  - condition 2
  TriggerConditions:
  - condition 1
  Drops:
  - <item/exp/droptable> <amount> <chance>
```

## ドロップテーブルオプション

### TotalItems: [number]

テーブルが生成するドロップ数を正確に定義します。
設定するとアイテムの確率が重みとして計算されます。

### MaxItems: [number]

生成されるドロップの最大数を定義します。
これのみが設定されている場合、最大数に達するまでリストを処理します。

### MinItems: [number]

生成されるドロップの最小数を定義します。
`MinItems`と`MaxItems`の両方を有効にすると、各テーブルエントリの確率が*重み*になります。

### BonusLevelItems: [number/range]

モブのレベルに基づいて生成されるドロップ数の修飾子。
`amount = amount + (mob_level * bonus_level_items)`
`TotalItems`、`MinItems`、または`MaxItems`のいずれかが設定されている必要があります。

### BonusLuckItems: [number/range]

キラーのラック統計に基づいて生成されるドロップ数の修飾子。
ラック属性、ラックベースのエンチャント/カース、ラックポーション効果で機能します。

## 例

### 基本的なドロップテーブルの例

```yaml
snow_loving_zombie:
  Type: zombie
  Health: 100
  Drops:
  - exp 75-125 1
  - rare_snowsword_droptable
```

このドロップテーブルは、モブが「ICE_PLAINS」バイオームで倒され、プレイヤーが20ブロック以内にいる場合のみ5%の確率でカスタム剣をドロップします：

```yaml
rare_snowsword_droptable:
  Conditions:
  - biome{b=ICE_PLAINS}
  - playerwithin{d=20}
  Drops:
  - snowsword 1 0.05
```

### ラック付きドロップテーブルの例

```yaml
LuckyDroptable:
  TotalItems: 5
  BonusLuckItems: 2to5
  Drops:
  - GOLD_NUGGET 1 1
  - DIAMOND 1 0.2
```

## 装備ドロップテーブル

ドロップテーブルを使用して装備セットアップを設定することも可能です。

```yaml
# ドロップテーブル設定
Example_EquipmentDropTable:
  Drops:
  - LEATHER_HELMET HELMET 1 1
  - LEATHER_CHESTPLATE CHEST 1 1
  - CHAINMAIL_CHESTPLATE CHEST 1 0.5
  - DIAMOND_CHESTPLATE CHEST 1 0.1
  - NETHERITE_CHESTPLATE CHEST 1 0.05

# モブ設定
ExampleMob:
  Type: ZOMBIE
  Equipment:
  - Example_EquipmentDropTable
```
