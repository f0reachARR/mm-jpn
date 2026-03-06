# pitch

**タイプ**: 🟦 エンティティ (Entity)

## 説明

エンティティのピッチ（上下の向き）をチェックします。

> *Checks if the pitch of the target entity is within a range*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `pitch` | p | The number range to match |  |

## 使用例

**例 1:**

```yaml
  Conditions:
  - pitch{p=-45to45} true
```

**例 2:**

```yaml
  Conditions:
  - pitch{p=>45} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/pitch)を基に日本語訳されています。
