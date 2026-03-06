# @TargetPredictedLocation (ターゲット予測位置ターゲッター)

## 概要
キャスターのターゲットが指定ティック後にいると予測される位置をターゲットにします。ターゲットの現在の移動速度に基づいて計算されます。

- **タイプ**: 単一場所ターゲッター
- **省略形**: `@targetPredictedLoc`, `@TPL`, `@PredictedTargetLocation`

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| maxdistance | max, distance, d | ターゲットの現在位置からの最大距離 | 64 |
| ticksPredicted | ticks, t | 何ティック先を予測するか | 20 |
| ignoreTransparent | it | 予測のレイトレースで透明なブロックを無視するか | true |

## 使用例
```yaml
ExampleSkill:
  Skills:
  - skill{s=TheFloorIsLava} @targetPredictedLoc{ticks=15}  # 15ティック後のターゲット予測位置にスキル発動
```

## 備考
- 移動中のターゲットを先読みして攻撃するのに使用します
- ブロックがある場合、予測位置はそのブロックで止まります
