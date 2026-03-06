# カスタムエンチャント (Enchantments)

MythicMobs では、カスタムエンチャントシステムを通じて独自のエンチャント効果を作成できます（一部プラグイン連携が必要）。

---

## バニラエンチャントの使い方

カスタムアイテムにバニラのエンチャントを付与する基本的な方法です。

```yaml
MyItem:
  Id: DIAMOND_SWORD
  Enchantments:
  - DAMAGE_ALL:5          # 鋭さ V
  - FIRE_ASPECT:2         # 火属性 II
```

---

## エンチャント名一覧

### 剣用エンチャント

| 名前 | 日本語名 | 最大レベル |
|------|---------|----------|
| `DAMAGE_ALL` | 鋭さ | V |
| `DAMAGE_UNDEAD` | スマイト | V |
| `DAMAGE_ARTHROPODS` | 虫特攻 | V |
| `KNOCKBACK` | 吹き飛ばし | II |
| `FIRE_ASPECT` | 火属性 | II |
| `LOOTING` | 幸運（剣） | III |
| `SWEEPING_EDGE` | 範囲攻撃強化 | III |

### 防具用エンチャント

| 名前 | 日本語名 | 最大レベル |
|------|---------|----------|
| `PROTECTION_ENVIRONMENTAL` | 保護 | IV |
| `PROTECTION_FIRE` | 耐火保護 | IV |
| `PROTECTION_FALL` | 落下耐性 | IV |
| `PROTECTION_EXPLOSIONS` | 爆発耐性 | IV |
| `PROTECTION_PROJECTILE` | 飛来物耐性 | IV |
| `THORNS` | 棘の鎧 | III |
| `DEPTH_STRIDER` | 水中歩行（ブーツ） | III |
| `FROST_WALKER` | 氷渡り（ブーツ） | II |
| `SOUL_SPEED` | 魂の速度（ブーツ） | III |
| `SWIFT_SNEAK` | 素早い忍び足（レギンス） | III |

### ツール用エンチャント

| 名前 | 日本語名 | 最大レベル |
|------|---------|----------|
| `EFFICIENCY` | 効率強化 | V |
| `SILK_TOUCH` | シルクタッチ | I |
| `FORTUNE` | 幸運（採掘） | III |

### 弓用エンチャント

| 名前 | 日本語名 | 最大レベル |
|------|---------|----------|
| `POWER` | 射力 | V |
| `FLAME` | 火矢 | I |
| `PUNCH` | 吹き飛ばし（弓） | II |
| `INFINITY` | 無限矢 | I |

### クロスボウ用エンチャント

| 名前 | 日本語名 | 最大レベル |
|------|---------|----------|
| `MULTISHOT` | 三連矢 | I |
| `QUICK_CHARGE` | 素早い装填 | III |
| `PIERCING` | 貫通 | IV |

### トライデント用エンチャント

| 名前 | 日本語名 | 最大レベル |
|------|---------|----------|
| `IMPALING` | 水棲特攻 | V |
| `RIPTIDE` | 乱流 | III |
| `LOYALTY` | 忠誠 | III |
| `CHANNELING` | 召雷 | I |

### 全アイテム共通エンチャント

| 名前 | 日本語名 | 最大レベル |
|------|---------|----------|
| `DURABILITY` | 耐久力 | III |
| `MENDING` | 修繕 | I |
| `BINDING_CURSE` | 束縛の呪い | I |
| `VANISHING_CURSE` | 消滅の呪い | I |

---

## 設定例

```yaml
BerserkerSword:
  Id: NETHERITE_SWORD
  Display: "&c&lバーサーカーの剣"
  Lore:
  - "&7圧倒的な力を秘めた剣"
  Enchantments:
  - DAMAGE_ALL:5
  - FIRE_ASPECT:2
  - KNOCKBACK:2
  - LOOTING:3
  - SWEEPING_EDGE:3
  - DURABILITY:3
  - MENDING:1
  Options:
    Unbreakable: true
    HideFlags: true
```

---

## 注意事項

- バニラのエンチャント制限（同時付与不可の組み合わせ）は MythicMobs では**無効**になります。
  - 例: `SILK_TOUCH` と `FORTUNE` を同時に付けることが可能です。
- エンチャントレベルはゲーム内の最大値を超えることができます（例: `DAMAGE_ALL:10`）。
- ただし、極端に高いレベルは一部の動作が期待通りにならない場合があります。

---

[← アイテム設定に戻る](Items.md) | [← ホームに戻る](../Home.md)
