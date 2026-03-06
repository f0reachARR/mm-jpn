# @SelfLocation (自己位置ターゲッター)

## 概要
キャスターの現在位置をターゲットにします。

- **タイプ**: 単一場所ターゲッター
- **省略形**: `@casterLocation`, `@bossLocation`, `@mobLocation`

## 属性
> *このターゲッターには属性がありません*

## 使用例
```yaml
ExampleSkill:
  Skills:
  - effect:particles @SelfLocation  # キャスターの位置にパーティクルを表示
```

## 備考
- エンティティではなく場所をターゲットにする場合に使用します
- `@Self` はエンティティをターゲットにしますが、こちらは位置をターゲットにします
