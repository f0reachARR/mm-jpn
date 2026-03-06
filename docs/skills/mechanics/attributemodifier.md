# AttributeModifier（属性修飾子追加）

## 説明

対象に属性修飾子（AttributeModifier）を追加します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| attribute | attr, a | 修飾するバニラ属性名 | |
| amount | v, value | 修飾量 | 1 |
| operation | op, o | 演算方式（`ADD_NUMBER`、`ADD_SCALAR`、`MULTIPLY_SCALAR_1`） | ADD_NUMBER |
| duration | d | 効果の継続時間（tick単位、0で永続） | 0 |
| name | n | 修飾子の識別名 | MythicMobs |
| slot | s | 効果を有効にする装備スロット（設定しない場合は常時有効） | |

## 使用例

```yaml
  Skills:
  - attributemodifier{attr=GENERIC_MOVEMENT_SPEED;amount=0.1;operation=ADD_SCALAR;d=100} @trigger ~onInteract
```

## エイリアス
- [x] attrmod
- [x] addattributemodifier
