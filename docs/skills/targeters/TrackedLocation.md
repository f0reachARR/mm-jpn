# @TrackedLocation (追跡位置ターゲッター)

## 概要
キャスターの追跡位置（`tracklocation` メカニクスで設定された位置）をターゲットにします。

- **タイプ**: 単一場所ターゲッター

## 属性
> *このターゲッターには属性がありません*

## 使用例
```yaml
ExampleSkill:
  Skills:
  - goto @TrackedLocation  # 追跡位置に移動
```

## 備考
- `tracklocation` メカニクスで事前に位置を設定しておく必要があります
- 任意の位置を記憶してスキルのターゲットにする場合に使用します
