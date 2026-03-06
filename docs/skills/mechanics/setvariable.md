# SetVariable（変数設定）

## 説明

変数の値を設定します。

## 属性

### Inheritable Attributes

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| variable | name, n, var, key, k | 変数名 |  |
| scope | s | The [scope](/skills/variables#variable-scopes) of the variable, e.g. where the variable will be located | SKILL<!--type:VariableScope--> |
| save |  | Whether the variable should save between reloads, reboots and disconnects. Does not apply to SKILL-scoped variables | false |
| duration | d, e, expire | How long (in ticks) the variable should last. Does not apply to SKILL-scoped variables | Infinite |

### Non-Inheritable Attributes

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| value | val, v, amount, a | 設定するスコア値 |  |
| type | t | The [type](/skills/variables#variable_types) of the variable. Set to STRING if you are using text instead of numbers | INTEGER<!--type:VariableType--> |

## エイリアス

- [x] setvar
- [x] variableset
<!--TAGS-->
<!--tag:Variable-->
