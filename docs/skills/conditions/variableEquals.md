# variableEquals

**タイプ**: 🟥 メタ (Meta)

## 説明

変数が指定された値と等しいかどうかをチェックします。

> *A condition that checks the value of a [variable](/Skills/Variables).*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `variable` | name, n, var, key, k | The name of the variable. Can optionally be prefixed with scope |  |
| `value` | val, v | The value that the variable must equal to return true. Must be applicable for type or the mechanic will fail. Should be surrounded in double-quotes if using spaces. Value can also include placeholders, even from PlaceholderAPI. |  |
| `scope` | s | The [scope](/Skills/Variables#variable-scopes) of the variable, e.g. where the variable is located |  |

## 使用例

**例 1:**

```yaml
BearMob:
  Skills:
  - skill:BearGrowl @PlayersInRadius{r=40} ~onTimer:60
```

**例 2:**

```yaml
BearGrowl:
  TargetConditions:
  - variableEquals{var=target.heardbear;value="yes"} cancel
  Skills:
  - message{m="&7You hear a growling noise..."}
  - setvariable{var=target.heardbear;value="yes";duration=6000}
```

**例 3:**

```yaml
PoisonStormDamage:
  Conditions:
  - varEquals{var=global.poison_storm;value="yes"}
  Skills:
  - potion{type=POISON;duration=100}
  - damage{amount=1;ignorearmor=true}
```

## エイリアス

- `variableeq`
- `varequals`
- `vareq`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/variableEquals)を基に日本語訳されています。
