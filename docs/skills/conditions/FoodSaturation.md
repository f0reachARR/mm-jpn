# FoodSaturation

**タイプ**: 🟦 エンティティ (Entity)

## 説明

ターゲットの食料満腹度をチェックします。

> *Checks the food saturation amount of the target*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `amount` | a, food, f, saturation, s | Range of amount of food saturation to check for | 0 |

## 使用例

```yaml
  TargetConditions:
  - FoodSaturation{a=<1} true
```

## エイリアス

- `hungerSaturation`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/FoodSaturation)を基に日本語訳されています。
