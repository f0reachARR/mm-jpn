# EnchantingExperience

**タイプ**: 🟦 エンティティ (Entity)

## 説明

エンチャント経験値をチェックします。

> *Checks the experience points that the target player has.*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `level` | l, amount, a | Checks against the experience points missing to reach the next level, in a range from 0 to 1. 0 is "no progress" and 1 is "next level". Accepts ranges. | 0 |

## 使用例

```yaml
  TargetConditions:
  - enchantingExperience{l=>0.2} true
```

## エイリアス

- `enchantingExp`
- `enchantExperience`
- `enchantExp`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/EnchantingExperience)を基に日本語訳されています。
