# EntityItemIsSimilar

**タイプ**: 🟦 エンティティ (Entity)

## 説明

エンティティのアイテムが指定されたアイテムと類似しているかどうかをチェックします。

> *Tests if the item entity is similar to an itemstack*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `item` | i, material, m, mm, mythicitem | The item to check against | DIRT |

## 使用例

```yaml
  TargetConditions:
  - entityitemissimilar{i=MyCustomItem} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/EntityItemIsSimilar)を基に日本語訳されています。
