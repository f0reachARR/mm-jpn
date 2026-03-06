# children

**タイプ**: 🟦 エンティティ (Entity)

## 説明

キャスターが持つ子供の数をテストします。

> *Checks how many children the caster has.*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `amount` | a | The amount of children to check for. Can accept ranged values. | 1 |

## 使用例

**例 1:**

```yaml
  Conditions:
  - children{a=1} true
```

**例 2:**

```yaml
  Conditions:
  - children{a=>2} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/children)を基に日本語訳されています。
