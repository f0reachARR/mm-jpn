# カスタムアイテム (Items)

MythicMobs では、独自のカスタムアイテムを作成できます。

---

## 概要

カスタムアイテムは `plugins/MythicMobs/Items/` フォルダ内の YAML ファイルに定義します。

---

## 基本構文

```yaml
MyItemName:
  Id: <マテリアル名>
  Display: "<表示名>"
  Lore:
  - "<説明文1>"
  - "<説明文2>"
  Amount: 1
  Data: 0
  Options:
    <オプション>
  Enchantments:
  - <エンチャント名>:<レベル>
  Attributes:
    <属性名>:
      Slot: <スロット>
      Amount: <量>
      Operation: <操作>
```

---

## 主要フィールド

### Id（マテリアル）

アイテムのベースとなる Minecraft のマテリアル名を指定します。

```yaml
Id: DIAMOND_SWORD
```

### Display（表示名）

アイテムの表示名です。カラーコードをサポートします。

```yaml
Display: "&6&l伝説の剣"
```

### Lore（説明文）

アイテムの説明文（ツールチップ）を設定します。

```yaml
Lore:
- "&7古代の鍛冶師が作りし名剣"
- "&7伝説の力を宿す"
- ""
- "&cダメージ: &f+15"
```

### Amount（数量）

デフォルトのスタック数。

```yaml
Amount: 1
```

---

## アイテムオプション

### Options セクション

```yaml
MyItem:
  Id: DIAMOND_SWORD
  Options:
    Unbreakable: true           # 耐久無限
    HideFlags: true             # フラグを非表示
    GlowingEffect: true         # グロー効果（エンチャントなしで輝く）
    Color: "255,0,0"            # 革防具の色 (R,G,B)
    PlayerProfile: <プレイヤー名>  # スキンのカスタマイズ（頭アイテム用）
    SkullOwner: <プレイヤー名>    # スカルの所有者
```

| オプション | 説明 |
|-----------|------|
| `Unbreakable` | 耐久値無限（NBTタグで設定） |
| `HideFlags` | エンチャント・属性・タグを非表示 |
| `GlowingEffect` | エンチャント効果なしで光らせる |
| `Color` | 革防具の色（R,G,B形式） |
| `SkullOwner` | プレイヤーヘッドのスキン所有者 |

---

## エンチャント

```yaml
Enchantments:
- DAMAGE_ALL:5              # 鋭さ V
- FIRE_ASPECT:2             # 火属性 II
- KNOCKBACK:2               # 吹き飛ばし II
- DURABILITY:3              # 耐久力 III
- LOOTING:3                 # 幸運 III
```

主なエンチャント名：

| エンチャント名 | 説明 |
|-------------|------|
| `DAMAGE_ALL` | 鋭さ（剣） |
| `DAMAGE_UNDEAD` | スマイト（アンデッドへの追加ダメージ） |
| `DAMAGE_ARTHROPODS` | 虫特攻 |
| `KNOCKBACK` | 吹き飛ばし |
| `FIRE_ASPECT` | 火属性 |
| `LOOTING` | 幸運（剣） |
| `SWEEPING_EDGE` | 範囲攻撃 |
| `PROTECTION_ENVIRONMENTAL` | 保護 |
| `PROTECTION_FIRE` | 耐火保護 |
| `PROTECTION_FALL` | 落下耐性 |
| `PROTECTION_EXPLOSIONS` | 爆発耐性 |
| `PROTECTION_PROJECTILE` | 飛来物耐性 |
| `THORNS` | 棘の鎧 |
| `EFFICIENCY` | 効率強化 |
| `SILK_TOUCH` | シルクタッチ |
| `FORTUNE` | 幸運（採掘） |
| `POWER` | 射力（弓） |
| `FLAME` | 火矢（弓） |
| `PUNCH` | 吹き飛ばし（弓） |
| `INFINITY` | 無限矢（弓） |
| `DURABILITY` | 耐久力 |
| `MENDING` | 修繕 |
| `BINDING_CURSE` | 束縛の呪い |
| `VANISHING_CURSE` | 消滅の呪い |
| `DEPTH_STRIDER` | 水中歩行 |
| `FROST_WALKER` | 氷渡り |
| `SOUL_SPEED` | 魂の速度 |
| `SWIFT_SNEAK` | 素早い忍び足 |
| `MULTISHOT` | 三連矢（クロスボウ） |
| `QUICK_CHARGE` | 素早い装填（クロスボウ） |
| `PIERCING` | 貫通（クロスボウ） |
| `IMPALING` | 水棲特攻（トライデント） |
| `RIPTIDE` | 乱流（トライデント） |
| `LOYALTY` | 忠誠（トライデント） |
| `CHANNELING` | 召雷（トライデント） |

---

## 属性 (Attributes)

アイテムに属性を追加して、装備時のステータスを変化させます。

```yaml
Attributes:
  GENERIC_ATTACK_DAMAGE:
    Slot: HAND
    Amount: 15
    Operation: ADD_NUMBER
  GENERIC_MOVEMENT_SPEED:
    Slot: FEET
    Amount: 0.05
    Operation: ADD_NUMBER
  GENERIC_MAX_HEALTH:
    Slot: CHEST
    Amount: 4
    Operation: ADD_NUMBER
```

| 属性名 | 説明 |
|--------|------|
| `GENERIC_ATTACK_DAMAGE` | 攻撃力 |
| `GENERIC_ATTACK_SPEED` | 攻撃速度 |
| `GENERIC_MAX_HEALTH` | 最大体力 |
| `GENERIC_MOVEMENT_SPEED` | 移動速度 |
| `GENERIC_ARMOR` | 防御力 |
| `GENERIC_ARMOR_TOUGHNESS` | 防御強度 |
| `GENERIC_KNOCKBACK_RESISTANCE` | ノックバック耐性 |
| `GENERIC_LUCK` | 幸運 |

### Operation の種類

| 操作 | 説明 |
|------|------|
| `ADD_NUMBER` | 値を加算する |
| `ADD_SCALAR` | 倍率として加算（ベース値 × 操作値） |
| `MULTIPLY_SCALAR_1` | ベース値を掛け合わせる |

---

## アイテムの取得コマンド

```
/mm items get <アイテム名>
/mm items get <アイテム名> <数量>
```

---

## 完全な設定例

```yaml
# plugins/MythicMobs/Items/LegendaryItems.yml

LegendarySword:
  Id: DIAMOND_SWORD
  Display: "&6&l伝説の剣 &e✦"
  Lore:
  - "&7古代の英雄が使いし伝説の剣"
  - ""
  - "&c⚔ 攻撃力: &f+15"
  - "&a❤ 体力増加: &f+4"
  - ""
  - "&e&l伝説級アイテム"
  Enchantments:
  - DAMAGE_ALL:5
  - FIRE_ASPECT:2
  - KNOCKBACK:2
  - LOOTING:3
  - DURABILITY:3
  Attributes:
    GENERIC_ATTACK_DAMAGE:
      Slot: HAND
      Amount: 15
      Operation: ADD_NUMBER
    GENERIC_MAX_HEALTH:
      Slot: HAND
      Amount: 4
      Operation: ADD_NUMBER
  Options:
    Unbreakable: true
    HideFlags: false
    GlowingEffect: false

AncientHelmet:
  Id: DIAMOND_HELMET
  Display: "&b&l古代の兜"
  Lore:
  - "&7古代文明が産んだ魔法の兜"
  - ""
  - "&a❤ 体力増加: &f+6"
  - "&7🛡 防御力強化"
  Enchantments:
  - PROTECTION_ENVIRONMENTAL:4
  - DURABILITY:3
  Attributes:
    GENERIC_MAX_HEALTH:
      Slot: HEAD
      Amount: 6
      Operation: ADD_NUMBER
    GENERIC_ARMOR:
      Slot: HEAD
      Amount: 3
      Operation: ADD_NUMBER
  Options:
    Unbreakable: true
```

---

## 関連ページ

- [アイテムオプション](Item-Options.md)
- [カスタムエンチャント](Enchantments.md)
- [ドロップ設定](../Drops/Drops.md)

---

[← ホームに戻る](../Home.md)
