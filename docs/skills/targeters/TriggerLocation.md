# @TriggerLocation (トリガー位置ターゲッター)

## 概要
スキルツリーをトリガーしたエンティティの位置をターゲットにします。

- **タイプ**: 単一場所ターゲッター

## 属性
> *このターゲッターには属性がありません*

## 使用例
```yaml
BobTheVengeful:
  Type: COW
  Skills:
  - lightning @TriggerLocation ~onDamaged  # 攻撃されたとき、攻撃者の位置に雷を落とす
```

## 備考
- `@Trigger` はエンティティをターゲットにしますが、こちらは位置をターゲットにします
