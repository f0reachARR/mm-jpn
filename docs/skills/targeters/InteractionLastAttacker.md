# @InteractionLastAttacker (最後の攻撃者ターゲッター)

## 概要
キャスターが `INTERACTION` タイプのエンティティである場合、最後にキャスターを攻撃したエンティティをターゲットにします。

- **タイプ**: 単一エンティティターゲッター
- **省略形**: `@lastAttacker`

## 属性
> *このターゲッターには属性がありません*

## 使用例
```yaml
ExampleInteractionEntity:
  Type: INTERACTION
  Skills:
  - ignite @interactionLastAttacker ~onTimer:100  # 最後に攻撃したエンティティに火をつける
```

## 備考
- キャスターが `INTERACTION` タイプでなければ機能しません
- Minecraftの `Interaction` エンティティ機能と連携しています
