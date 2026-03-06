# GiveExperienceLevels（経験値レベル付与）

## 説明

ターゲットプレイヤーに経験値レベルを付与します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| amount | a | 付与するレベル数 | 1 |

## 使用例

```yaml
  Skills:
  - giveexperiencelevels{amount=5} @trigger ~onInteract
```

## エイリアス
- [x] giveexplevels
- [x] givexp
- [x] givexplevels
- [x] gel
