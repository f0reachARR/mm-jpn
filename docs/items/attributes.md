# アイテム属性 (Item Attributes)

アイテムのAttributesセクションはMinecraftの属性システムを処理します。アイテムを持っている/着用しているエンティティに、スロットに応じた異なる属性を適用できます。

## フォーマット

```yml
Item:
  Id: item_id
  Attributes:
    [Slot]:
      [Attribute]: [value] <operation>
```

## スロット

| スロット | 説明 |
|--------|------|
| All | すべてのスロットに指定された属性を適用します |
| MainHand | アイテムがメインハンドに持たれている場合のみ属性が適用されます |
| OffHand | アイテムがオフハンドに持たれている場合のみ属性が適用されます |
| Head | アイテムが頭スロットに装着されている場合のみ属性が適用されます |
| Chest | アイテムが胸/胴体スロットに装着されている場合のみ属性が適用されます |
| Legs | アイテムが脚スロットに装着されている場合のみ属性が適用されます |
| Feet | アイテムが足スロットに装着されている場合のみ属性が適用されます |

## 値（Value）

絶対値または相対値の両方を入力できます：

```yaml
# 絶対値
Damage: 10 ADD

# 相対値（%記号を使用）
Damage: 10% ADD
```

## オペレーション

| オペレーション | エイリアス | 説明 |
|------------|---------|------|
| ADD | 0, ADD_NUMBER | ベース値に指定された値を加算または減算します |
| MULTIPLY_BASE | 1, ADD_SCALAR | すべての修飾子の量の合計でベース値を乗算します |
| MULTIPLY | 2, MULTIPLY_SCALAR | MULTIPLY_BASEに似ていますが、すべての修飾子の量を加算するのではなく乗算します |

## 利用可能な属性

### ATTACK_DAMAGE (攻撃ダメージ)

近接攻撃で与えるダメージを設定します。1ダメージは防具なしで0.5ハートのダメージに等しいです。

```yml
custom_item:
  Id: stick
  Attributes:
    MainHand:
      ATTACK_DAMAGE: 10 ADD
```

### MAX_HEALTH (最大HP)

アイテムを持っている/着用しているときのユーザーの最大HPを設定します。1HPは0.5ハートです。

```yml
custom_item:
  Id: diamond_chestplate
  Attributes:
    Chest:
      MAX_HEALTH: 4 ADD
```

### MOVEMENT_SPEED (移動速度)

エンティティが移動できる速度。

```yml
custom_item:
  Id: wooden_sword
  Attributes:
    All:
      MOVEMENT_SPEED: -0.2 MULTIPLY_BASE
```

### ATTACK_SPEED (攻撃速度)

攻撃強度の回復レートを決定します。

```yml
custom_item:
  Id: stick
  Attributes:
    MainHand:
      ATTACK_SPEED: 0.1 MULTIPLY
```

### KNOCKBACK_RESISTANCE (ノックバック耐性)

攻撃や発射物からのノックバックを0.0（0%耐性）から1.0（100%耐性）で決定します。

```yml
custom_item:
  Id: diamond_chestplate
  Attributes:
    Chest:
      KNOCKBACK_RESISTANCE: 0.5 ADD
```

### ARMOR (アーマー)

アーマー防御ポイントを定義します。1アーマーは0.5アーマープレートに等しいです。

```yml
custom_item:
  Id: diamond_chestplate
  Attributes:
    Chest:
      ARMOR: 8 ADD
```

### ARMOR_TOUGHNESS (アーマー耐久性)

アーマー属性のダメージ軽減割合を変更します。

```yml
custom_item:
  Id: diamond_chestplate
  Attributes:
    Chest:
      ARMOR_TOUGHNESS: 2 ADD
```

### LUCK (ラック)

アイテムのラック修飾子を設定します。ルートテーブルの結果とモブドロップに影響します。

```yml
custom_item:
  Id: stick
  Attributes:
    OffHand:
      LUCK: 5 ADD
```

### SCALE (スケール)

エンティティのサイズの乗数です。

```yml
custom_item:
  Id: wooden_sword
  Attributes:
    All:
      SCALE: 2 ADD
```

### JUMP_HEIGHT (ジャンプ高さ)

エンティティがジャンプするときの初期垂直速度。

```yml
custom_item:
  Id: boots
  Attributes:
    Feet:
      JUMP_HEIGHT: 1 ADD
```

### FLYING_SPEED (飛行速度)

飛行速度の修飾子です。

```yml
custom_item:
  Id: wooden_sword
  Attributes:
    All:
      FLYING_SPEED: 1 ADD
```

## 例

### カスタム戦士の剣

```yml
WarriorSword:
  Id: DIAMOND_SWORD
  Display: '&b戦士の剣'
  Attributes:
    MainHand:
      ATTACK_DAMAGE: 8 ADD
      ATTACK_SPEED: -0.5 ADD
      MAX_HEALTH: 2 ADD
      MOVEMENT_SPEED: -0.05 ADD
```

### タンクの鎧

```yml
TankArmor:
  Id: NETHERITE_CHESTPLATE
  Display: '&8タンクの甲冑'
  Attributes:
    Chest:
      MAX_HEALTH: 10 ADD
      ARMOR: 5 ADD
      ARMOR_TOUGHNESS: 3 ADD
      KNOCKBACK_RESISTANCE: 0.3 ADD
      MOVEMENT_SPEED: -0.1 MULTIPLY_BASE
```
