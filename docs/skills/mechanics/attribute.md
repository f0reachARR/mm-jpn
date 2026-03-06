# Attribute（属性設定）

## 説明

ターゲットエンティティに属性を設定します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| attribute | attr, a | 設定するバニラ属性名 | |
| amount | v, value | 属性の値 | 1 |
| duration | d | 効果の継続時間（tick単位、0で永続） | 0 |

## 使用例

```yaml
  Skills:
  - attribute{attr=GENERIC_MAX_HEALTH;amount=40} @trigger ~onInteract
```

## エイリアス
- [x] setattribute
