# VariableSet（変数設定）

## 説明

変数の値を設定します。変数は恒久的または一時的に設定でき、条件やプレースホルダーと組み合わせてデータを保存するために使用されます。

> `setvariable` メカニックのエイリアスです。詳細は [SetVariable](/skills/mechanics/setvariable) を参照してください。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| variable | var, name, n, key, k | 変数名（スコープのプレフィックス付けも可） | |
| scope | s | 変数の[スコープ](/skills/variables#variable-scopes) | SKILL |
| value | val, v, amount, a | 設定する値 | |
| type | t | 変数の[タイプ](/skills/variables#variable_types)（テキストの場合は STRING） | INTEGER |
| save | | リロード・再起動時に変数を保存するか（SKILLスコープには適用されない） | false |
| duration | d, e, expire | 変数の持続時間（tick）（SKILLスコープには適用されない） | Infinite |

## 使用例

```yaml
  Skills:
  - variableset{var=skill.myVar;value=10;type=INTEGER} ~onInteract
  - variableset{var=caster.name;value="<target.name>";type=STRING} @self
```

## エイリアス
- [x] setvariable
- [x] setvar
- [x] varset
