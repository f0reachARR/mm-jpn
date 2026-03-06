# @SelfEyeLocation (自己目線位置ターゲッター)

## 概要
キャスターの目線の位置をターゲットにします。

- **タイプ**: 単一場所ターゲッター
- **省略形**: `@eyeDirection`, `@casterEyeLocation`, `@bossEyeLocation`, `@mobEyeLocation`

## 属性
> *このターゲッターには属性がありません*

## 使用例
```yaml
ExampleSkill:
  Skills:
  - effect:particles @SelfEyeLocation{fo=3}  # 目線位置にパーティクルを表示
```

## 備考
- 足元ではなく頭（目線）の位置をターゲットにします
- ビームや視線に基づいたスキルに適しています
