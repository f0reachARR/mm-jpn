# @SpawnLocation (スポーン位置ターゲッター)

## 概要
ワールドのスポーン位置をターゲットにします。

- **タイプ**: 単一場所ターゲッター

## 属性
> *このターゲッターには属性がありません*

## 使用例
```yaml
ExampleSkill:
  Skills:
  - teleport @SpawnLocation  # ワールドのスポーン地点にテレポート
```

## 備考
- ワールドのスポーンポイント（`/setworldspawn` で設定されたもの）をターゲットにします
- `@CasterSpawnLocation` とは異なり、ワールドのスポーン地点を使用します
