# EntityItemType

**タイプ**: 🟦 エンティティ (Entity)

## 説明

エンティティのアイテムタイプをチェックします。

> *Tests the type of the targeted entity item*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `material` | mat, m, type, types, t | A list of items to match |  |

## 使用例

```yaml
  TargetConditions:
  - entityItemType{m=STONE} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/EntityItemType)を基に日本語訳されています。
