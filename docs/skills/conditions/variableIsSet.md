# variableIsSet

**タイプ**: 🟥 メタ (Meta)

## 説明

変数が設定されているかどうかをチェックします。

> *Checks if the given [variable](/Skills/Variables) is set.*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `variable` | name, n, var, key, k | The name of the variable. Can optionally be prefixed with scope |  |
| `scope` | s | The [scope](/Skills/Variables#variable-scopes) of the variable, e.g. where the variable is located |  |

## 使用例

```yaml
  Conditions:
  - variableisset{var=target.dazed} true
```

## エイリアス

- `varisset`
- `varset`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/variableIsSet)を基に日本語訳されています。
