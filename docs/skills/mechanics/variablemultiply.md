# VariableMultiply（変数乗算）

## 説明

変数の現在値に指定した値を乗算します。

> このメカニックは [SetVariable](skills/mechanics/setvariable) メカニックのすべての継承可能な属性を継承します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| amount | a, value, val, v | 乗算する値 | 1 |
| variable | var, name, n, key, k | 変数名 | |
| scope | s | 変数の[スコープ](/skills/variables#variable-scopes) | SKILL |

## 使用例

```yaml
  Skills:
  - variablemultiply{var=skill.counter;amount=2} ~onInteract
```

## エイリアス
- [x] multiplyVariable
- [x] varMultiply
- [x] multiplyVar
