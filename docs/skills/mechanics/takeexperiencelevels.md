# TakeExperienceLevels（経験値レベル剥奪）

## 説明

ターゲットプレイヤーから経験値レベルを剥奪します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| amount | a | 剥奪するレベル数 | 1 |

## 使用例

```yaml
  Skills:
  - takeexperiencelevels{amount=3} @trigger ~onInteract
```

## エイリアス
- [x] takeexplevels
- [x] takexplevels
- [x] tel
