# FoodLevel

**タイプ**: 🟦 エンティティ (Entity)

## 説明

ターゲットの食料レベルをチェックします。

> *Checks the food amount of the target*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `amount` | a, food, f | Range of amount of food to check for | 0 |

## 使用例

```yaml
  TargetConditions:
  - FoodLevel{a=<10} true
```

## エイリアス

- `hunger`
- `food`
- `hungerlevel`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/FoodLevel)を基に日本語訳されています。
