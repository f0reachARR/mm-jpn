# variableInRange

**タイプ**: 🟥 メタ (Meta)

## 説明

変数が指定された範囲内かどうかをチェックします。

> *Checks if the given numeric variable is within a certain range.*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `variable` | name, n, var, key, k | Variable to match, optionally prefixed by a scope |  |
| `value` | val, v, range, r | A number range to match |  |
| `scope` | s | The [scope](/Skills/Variables#variable-scopes) of the variable, e.g. where the variable is located |  |

## 使用例

```yaml
ShootCheck:
  Cooldown: 0
  Conditions:
  - variableInRange{var=caster.shootsLeft;value=>0} castInstead ShootThemUp
  Skills:
  - message{m="&7Reloading..."} @self
  - delay 0
  - setskillcooldown{skill=ShootCheck;seconds=2} @self
  - delay 20
  - setvariable{var=caster.shootsLeft;value=10} @self
  - message{m="&7Reloaded!"} @self
```

## エイリアス

- `varinrange`
- `varrange`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/variableInRange)を基に日本語訳されています。
