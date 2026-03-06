# AnimateArmorStand（アーマースタンドアニメーション）

## 説明

アーマースタンドをアニメーションさせます。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| headPose | head, hp | アーマースタンドの頭部のポーズ（x,y,z 形式） | 0,0,0 |
| bodyPose | body, bp | アーマースタンドの胴体のポーズ | 0,0,0 |
| leftArmPose | leftArm, la, lap | アーマースタンドの左腕のポーズ | 0,0,0 |
| rightArmPose | rightArm, ra, rap | アーマースタンドの右腕のポーズ | 0,0,0 |
| leftLegPose | leftLeg, ll, llp | アーマースタンドの左脚のポーズ | 0,0,0 |
| rightLegPose | rightLeg, rl, rlp | アーマースタンドの右脚のポーズ | 0,0,0 |
| duration | d | アニメーションの継続時間（tick単位） | 0 |
| delay | del | アニメーション開始前の遅延時間（tick単位） | 0 |

## 使用例

```yaml
  Skills:
  - animatearmorstand{headPose=0,90,0;duration=20} @self ~onTimer:20
```

## エイリアス
- [x] animateAS
- [x] aAS
