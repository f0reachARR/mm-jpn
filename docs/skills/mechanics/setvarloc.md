# SetVarLoc（位置変数設定）

## 説明

ターゲット位置を変数として保存します。位置変数を設定します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| variable | var, name, n, key, k | 変数名。スコープのプレフィックスを付けることができます | |
| scope | s | 変数の[スコープ](/skills/variables#variable-scopes) | SKILL |

## 使用例

```yaml
  Skills:
  - setvarloc{var=skill.savedLocation} @self ~onTimer:20
```
