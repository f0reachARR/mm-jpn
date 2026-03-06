# HealthPercent

**タイプ**: 🟦 エンティティ (Entity)

## 説明

ターゲットのHP割合に一致します。

> *Matches the target's health percentage or multiplier*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `percent` | p, healthpercent, hp | The health percentage or multiplier to check for (e.g., 50% or 0.5) | 0 |
| `includeabsorption` | ia | 吸収に関連するHPを計算に含めるかどうか | false |

## 使用例

**例 1:**

```yaml
# Exactly at 50% health
Conditions:
- healthpercent{p=50%} true
```

**例 2:**

```yaml
# Below 50% health
Conditions:
- healthpercent{p=<50%} true
```

**例 3:**

```yaml
# Above 10% health
Conditions:
- healthpercent{p=>0.1} true
```

## エイリアス

- `hppercent`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/HealthPercent)を基に日本語訳されています。
