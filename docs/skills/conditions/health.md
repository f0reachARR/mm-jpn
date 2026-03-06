# health

**タイプ**: 🟦 エンティティ (Entity)

## 説明

ターゲットのHPに一致します。

> *Matches the target's health*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `health` | h, amount, a | チェックするHPの範囲 | 0 |
| `includeabsorption` | ia | 吸収に関連するHPを計算に含めるかどうか | false |

## 使用例

**例 1:**

```yaml
Conditions:
- health{h=50} true
```

**例 2:**

```yaml
# Below 50 health
Conditions:
- health{h=<50} true
```

**例 3:**

```yaml
# Above 10 health
Conditions:
- health{h=>10} true
```

## エイリアス

- `hp`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/health)を基に日本語訳されています。
