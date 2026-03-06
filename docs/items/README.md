# アイテム (Items)

MythicMobsでカスタムアイテムを作成するのは非常に簡単です。
ただし、モブやスキルとは異なり、このプラグインで作成されたアイテムには特別またはユニークなオプションはありません。
MythicMobsで作成するアイテムはすべてMinecraftコマンドでも作成できますが、MythicMobs設定を使用した方がずっと快適です。

必要なのは`内部名（internal_name）`と`Id`のみです。他のすべてのオプション/属性は完全にオプションです。

`\plugins\MythicMobs\Items`フォルダにいくつでもファイルを作成でき、ファイル名は.ymlで終わる限り何でも構いません。

## アイテム設定の詳細

### 内部名（Internal_Name）

この文字列はMythicMobs内でアイテムを参照する方法で、任意の名前を使用できます。
英数字である必要があり、**スペースは使用不可**。

```yml
example_item:
```

### ID（Id）

アイテムのベースマテリアル。[こちら](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)にリストされている有効なマテリアルを使用できます。

```yml
example_item:
  Id: leather_chestplate
```

### テンプレート（Template）

アイテムは他のアイテムを参照しながら[テンプレート](../mobs/templates.md)を使用できます。

```yaml
MyItem:
  Template: MyOtherItem
```

### 表示名（Display）

アイテムの表示名を設定します。

```yml
example_item:
  Id: leather_chestplate
  Display: <green>サンプルアイテム</green>
```

### 説明文（Lore）

アイテムの説明文を設定します。`{min-max}`、`<random.#to#>`、または`<random.float.#to#>`を使用してランダムな数値を生成できます。

```yml
example_item:
  Id: leather_chestplate
  Lore:
    - <rainbow>この行は虹色です</rainbow>
    - <red>この行は赤いはずです</red>
    - ランダムな数値: <random.-1to50>
```

### カスタムモデルデータ（CustomModelData）

アイテムにCustomModelDataタグを設定します。`Model`は`CustomModelData`のエイリアスです。

```yml
example_item:
  Id: leather_chestplate
  CustomModelData: 12345
```

### 最大耐久値（MaxDurability）

アイテムの最大使用回数を変更します。スタックできないアイテムである必要があります。

```yaml
example_item:
  Id: diamond_sword
  MaxDurability: 600
```

### 耐久値（Durability）

アイテムから差し引く耐久値の量を設定します。

```yml
example_item:
  Id: diamond_sword
  Durability: 100
```

### 属性（Attributes）

特定のアーマースロットにアイテム属性を追加できる特別なフィールド。
[アイテム属性](attributes.md)を参照してください。

```yml
example_item:
  Id: leather_chestplate
  Attributes:
    Chest:
      Health: 25
```

### 数量（Amount）

このアイテムがプラグインによって呼び出された際のデフォルトのアイテム数を設定します。

```yml
example_item:
  Id: leather_chestplate
  Amount: 1
```

### オプション（Options）

多数のサブオプションを持つ特別なフィールド。
[アイテムオプション](options.md)を参照してください。

```yml
example_item:
  Id: leather_chestplate
  Options:
    AppendType: true
    Color: 255,0,0
```

### エンチャント（Enchantments）

任意のアイテムに任意のエンチャントを付与できます。
[エンチャント](enchantments.md)ページも参照してください。

```yml
example_item:
  Id: leather_chestplate
  Enchantments:
    - PROTECTION_ENVIRONMENTAL:2
    - THORNS:3
```

### 非表示（Hide）

アイテムのツールチップから特定の情報を非表示にできる特別なフィールド。

```yml
example_item:
  Id: leather_chestplate
  Hide:
    - ATTRIBUTES
    - ENCHANTS
```

### ポーション効果（PotionEffects）

アイテムのポーション効果を設定します。ベースアイテムがポーション、スプラッシュポーション、持続ポーション、または先端矢でない場合、これらの効果は何もしません。

```yml
example_item:
  Id: potion
  PotionEffects:
    - CONFUSION 100 2
```

### バナーレイヤー（BannerLayers）

バナーまたは盾のバナーレイヤーを設定します。

```yml
example_item:
  Id: yellow_banner
  BannerLayers:
    - RED BASE
    - WHITE CURLY_BORDER
```

### NBT

アイテムにNBTタグを設定します。

```yml
example_item:
  Id: STICK
  NBT:
    name1: int/123
    name2: sometext1
```

### 食料（Food）

アイテムの食料コンポーネントを設定します。機能するには[Consumable](#consumable-消費可能)の設定が必要です。

```yaml
NetheritePops:
  Material: NETHERITE_SCRAP
  Display: '美味しいスクラップ'
  Food:
    Nutrition: 2
    Saturation: 2
    CanAlwaysEat: true
```

## サブページ

- [属性](attributes.md)
- [エンチャント](enchantments.md)
- [オプション](options.md)
- [ポーション](potions.md)
- [バナーレイヤー](banner-layers.md)
- [アイテムマッチャー](item-matcher.md)
- [花火](firework.md)
