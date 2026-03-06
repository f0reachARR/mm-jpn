# damagetag

**タイプ**: 🟦 エンティティ (Entity)

## 説明

ダメージタグをチェックします。

> *Checks whether the damage that caused the current skill tree has a specific tag*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `tag` | t | The tag to check against |  |
| `value` | val, v, b, bool, boolean | If true, checks for the presence of the tag<br>If false, checks for its absence | true |

## 使用例

```yaml
Conditions:
- damageTag{tag=WITCHCURSES}
```

## エイリアス

- `damagehastag`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/damagetag)を基に日本語訳されています。
