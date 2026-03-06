# HasAuraType

**タイプ**: 🟦 エンティティ (Entity)

## 説明

ターゲットエンティティが指定されたタイプのオーラを持っているかどうかをチェックします。

> *Checks if the target entity has the given aura type*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `auragroup` | auratype, group, type, t, g | The aura type to check for |  |

## 使用例

**例 1:**

```yaml
  Skills:
  - aura{auraName=NotMeThisTime;auratype=Example;d=100} @self
```

**例 2:**

```yaml
  Conditions:
  - hasAuraType{type=Example} true
```

## エイリアス

- `hasbufftype`
- `hasdebufftype`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/HasAuraType)を基に日本語訳されています。
