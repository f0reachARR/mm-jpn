# bowtension

**タイプ**: 🟦 エンティティ (Entity)

## 説明

弓の引き具合をチェックします。

> *Checks the bow tension of when an entity shoots from a bow*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `force` | f, value, v, val | The value of the force/tension to check for. Accepts ranged float values, but only in a range from 0 to 1 | >0 |

## 使用例

```yaml
  Conditions:
  - bowtension{value=>0.5} true
```

## エイリアス

- `bowshoottension`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/bowtension)を基に日本語訳されています。
