# @LivingInWorld (ワールド内全エンティティターゲッター)

## 概要
キャスターのワールド内にいるすべての生きているエンティティをターゲットにします。

- **タイプ**: 複数エンティティターゲッター
- **省略形**: `@EIW`, `@allinworld`, `@livingentitiesinworld`, `@entitiesinworld`

## 属性
> *このターゲッターには属性がありません*

## 使用例
```yaml
EntityCount:
  Skills:
  # ワールド内のエンティティ数を変数に保存してメッセージ表示
  - setvariable{var=skill.count;val=<skill.targets>} @LivingInWorld
  - message{m="現在のワールドには <skill.var.count> 体のエンティティがいます"} @self
```

## 備考
- パフォーマンスへの影響が大きいため、使用は慎重に行ってください
- ワールド全体のすべての生きているエンティティに影響を与えます
