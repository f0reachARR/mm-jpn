# @UniqueIdentifier (UUID ターゲッター)

## 概要
UUIDで特定のエンティティをターゲットにします。プレースホルダーを使用できます。

- **タイプ**: 単一エンティティターゲッター
- **省略形**: `@UUID`

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| uuid | u | エンティティのUUID（プレースホルダー使用可） | 0 |

## 使用例
```yaml
VengefulMob:
  Type: ZOMBIE
  Skills:
  # 最初に攻撃したエンティティのUUIDを変数に保存
  - setvariable{var=caster.targetedentity;type=STRING;val=<trigger.uuid>} @self ~onDamaged =100% ?~isLiving
  # 10秒ごとにそのエンティティに火をつける
  - ignite @UniqueIdentifier{uuid=<caster.var.targetedentity>} ~onTimer:200 ?variableisset{var=caster.targetedentity}
```

## 備考
- ターゲッターフィルターに関係なく、あらゆるエンティティをターゲットにできます
- エンティティが既にアンロードされている場合は機能しません
