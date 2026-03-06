# @InteractionLastInteract (最後のインタラクター ターゲッター)

## 概要
キャスターが `INTERACTION` タイプのエンティティである場合、最後にキャスターとインタラクトしたエンティティをターゲットにします。

- **タイプ**: 単一エンティティターゲッター
- **省略形**: `@lastInteract`

## 属性
> *このターゲッターには属性がありません*

## 使用例
```yaml
ExampleInteractionEntity:
  Type: INTERACTION
  Skills:
  - ignite @interactionLastInteract ~onTimer:100  # 最後にインタラクトしたエンティティに火をつける
```

## 備考
- キャスターが `INTERACTION` タイプでなければ機能しません
- 右クリックによるインタラクションを検知します
