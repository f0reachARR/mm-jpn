# chance

**タイプ**: 🟥 メタ (Meta)

## 説明

メタスキルが実行される確率を設定します。

> *Sets the probability of the metaskill being executed.*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `chance` | c | The floating value which denotes the chance. It can range between 0 and 1, with 0 being a 0% chance and 1 being a 100% chance | 0.5 |

## 使用例

**例 1:**

```yaml
Conditions:
  - chance{chance=0.3} true
```

**例 2:**

```yaml
Conditions:
  - chance{chance=0.3} false
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/chance)を基に日本語訳されています。
