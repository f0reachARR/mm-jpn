# Potion（ポーション効果）

## 説明

ターゲットにポーション効果を適用します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| type | t, effect | \1の名前 | SLOW<!--type:PotionEffectType--> |
| duration | d | 持続時間（tick） | 100 |
| level | lvl, l | \1の名前 | 0 |
| force | overwrite, ow, override, or | Whether not to override the current potion effect or not. | false |
| hasParticles | particles, p | Whether not to show the status effect particles. | true |
| hasIcon | icon,  i | Whether not to show the status effect icon. | true |
| ambientparticles | ambient, a | アンビエントエフェクトを表示するか | false |
