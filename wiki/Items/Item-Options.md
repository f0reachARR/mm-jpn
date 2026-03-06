# アイテムオプション (Item Options)

カスタムアイテムの `Options` セクションで様々な動作をカスタマイズできます。

---

## オプション一覧

| オプション | 型 | 説明 |
|-----------|-----|------|
| `Unbreakable` | 真偽値 | アイテムを耐久無限にする |
| `HideFlags` | 真偽値 / 整数 | アイテム情報フラグを非表示にする |
| `GlowingEffect` | 真偽値 | エンチャントなしでアイテムを輝かせる |
| `Color` | 文字列 | 革防具の色（R,G,B形式） |
| `SkullOwner` | 文字列 | スカルヘッドのプレイヤー名 |
| `PlayerProfile` | 文字列 | カスタムスキンのプレイヤー名（頭アイテム用） |
| `CanPlaceOn` | リスト | 置けるブロックの制限（アドベンチャーモード用） |
| `CanDestroy` | リスト | 壊せるブロックの制限（アドベンチャーモード用） |
| `CustomModelData` | 整数 | カスタムモデルデータ（リソースパック連携） |

---

## 詳細説明

### Unbreakable（耐久無限）

アイテムに `Unbreakable` NBTタグを設定し、耐久値が減らなくなります。

```yaml
Options:
  Unbreakable: true
```

### HideFlags（フラグ非表示）

アイテムのツールチップに表示される情報を非表示にします。

`true` にすると全フラグを非表示。整数値でビットフィールドを指定することも可能。

```yaml
Options:
  HideFlags: true       # 全フラグを非表示
```

フラグのビット値：

| ビット値 | 非表示にする情報 |
|---------|--------------|
| `1` | エンチャント |
| `2` | 属性（Attributes） |
| `4` | 耐久無限 |
| `8` | CanDestroy |
| `16` | CanPlaceOn |
| `32` | その他 |
| `63` | 全て |

### GlowingEffect（グロー効果）

エンチャントがなくてもアイテムが輝くように見せます（エンチャントは実際には付いていません）。

```yaml
Options:
  GlowingEffect: true
```

### Color（革防具の色）

革の防具アイテムの色を RGB で指定します。

```yaml
Options:
  Color: "255,0,0"       # 赤色
  Color: "0,0,255"       # 青色
  Color: "0,255,0"       # 緑色
  Color: "128,0,128"     # 紫色
```

### SkullOwner（スカル所有者）

プレイヤーヘッドアイテムのスキンを設定します。

```yaml
Id: PLAYER_HEAD
Options:
  SkullOwner: Notch      # Notch のスキンを使用
```

### CustomModelData（カスタムモデルデータ）

リソースパックと連携してカスタムモデルを使用するためのデータを設定します。

```yaml
Options:
  CustomModelData: 1001   # リソースパックで定義したモデル番号
```

### CanPlaceOn / CanDestroy（アドベンチャーモード用）

アドベンチャーモードでのブロック設置・破壊制限。

```yaml
Options:
  CanPlaceOn:
  - STONE
  - DIRT
  CanDestroy:
  - OAK_LOG
  - STONE
```

---

## 使用例

```yaml
MagicWand:
  Id: STICK
  Display: "&d魔法の杖"
  Lore:
  - "&7魔法使いの証"
  Options:
    Unbreakable: true
    HideFlags: true
    GlowingEffect: true
    CustomModelData: 2001

ColoredArmor:
  Id: LEATHER_CHESTPLATE
  Display: "&4赤い革鎧"
  Options:
    Color: "200,30,30"
    Unbreakable: false

SpecialHead:
  Id: PLAYER_HEAD
  Display: "&bエリートの首"
  Options:
    SkullOwner: Notch
```

---

[← アイテム設定に戻る](Items.md) | [← ホームに戻る](../Home.md)
