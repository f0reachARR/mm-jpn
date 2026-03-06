# @PlayerByName (名前指定プレイヤーターゲッター)

## 概要
名前で特定のプレイヤーをターゲットにします。プレースホルダーを使用できます。

- **タイプ**: 単一エンティティターゲッター
- **省略形**: `@specificplayer`

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| name | n | プレイヤーの名前（プレースホルダー使用可） | CarsonJF |

## 使用例
```yaml
VengefulMob:
  Type: ZOMBIE
  Skills:
  # 最初に攻撃したプレイヤーの名前を変数に保存
  - setvariable{var=caster.targetedplayer;type=STRING;val=<trigger.name>} @self ~onDamaged =100% ?~isPlayer
  # 10秒ごとにそのプレイヤーに火をつける
  - ignite @PlayerByName{name=<caster.var.targetedplayer>} ~onTimer:200 ?variableisset{var=caster.targetedplayer}
```

## 備考
- 変数やプレースホルダーと組み合わせることで動的にターゲットを変更できます
- プレイヤーがオフラインの場合は機能しません
