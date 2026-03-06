# stance

**タイプ**: 🟦 エンティティ (Entity)

## 説明

エンティティの現在のスタンスをテストします。

> *Checks the stance of the target mob.*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `stance` | s | The stance to match | DEFAULT |
| `strict` | str | Whether to match exactly. Checks if the current stance contains this word if set to false | true |

## 使用例

```yaml
  Conditions:
  - stance{s=CombatStance;str=true} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/stance)を基に日本語訳されています。
