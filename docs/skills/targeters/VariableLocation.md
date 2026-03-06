# @VariableLocation (変数位置ターゲッター)

## 概要
指定した変数に保存されている位置をターゲットにします。位置変数は `SetVariableLocation` メカニクスで設定できます。

- **タイプ**: 単一場所ターゲッター
- **省略形**: `@varLocation`

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| variable | name, n, var, key, k | 変数の名前 | |
| scope | s | 変数のスコープ（名前に `スコープ.名前` 形式で含めることも可能） | |

## 使用例
```yaml
ExampleSkill:
  Skills:
  - setvarloc{var=caster.1;v=@targetlocation} @self          # ターゲット位置を変数に保存
  - particle{y=2} @VariableLocation{var=caster.1}             # 保存した位置にパーティクルを表示
```

## 備考
- 位置を記憶して後で参照する複雑なスキルに使用します
- `SetVariableLocation` メカニクスとセットで使用します
