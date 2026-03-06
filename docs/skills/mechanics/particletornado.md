# ParticleTornado（パーティクル竜巻）

## 説明

ターゲットに持続的なパーティクルの「竜巻」を描きます。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| maxradius | mr | Max radius of the highest tornado âdiskâ shape | 3 |
| yoffset | yo | \1の名前 | 0.8 |
| height | h | # of disks desired * 2 + 1 | 4 |
| interval | i | How fast the particles vertically render. This can be experimented with ârotationspeedâ as well | 4 |
| duration | d | Duration of the effect in ticks | 200 |
| rotationspeed | rs | How fast the particles will horizontally render. This can be experimented with âintervalâ as well | 0.04 |
| sliceheight | sh | Any value below 1 will cause an incomplete tornado, while anything above 10 will cause different sized spheres to appear in a strange order. This has yet to be fully defined | 64 |
| stoponcasterdeath | scd | Whether the effect should stop upon the death of its caster | true |
| stoponentitydeath | sed | Whether the effect should stop upon the death of the entity it is used on | true |
| cloudparticle | cp | \1の名前 | largeexplode<!--type:Particle--> |
| cloudsize | cs | ターゲット周囲の半径 | 5 |
| cloudamount | ca | How many particles will appear at each randomly generated cloud location. | 1 |
| cloudhspread | chs | \1の名前 | 1 |
| cloudvspread | cvs | \1の名前 | 1.8 |
| cloudpspeed | cps | Speed of the playing of the cloud particles | 2 |
| cloudyoffset | cyo | Y Offsetting of the entire tornado. (1 + your desired height) | 1.8 |

## エイリアス

- [x] effect:particletornado
- [x] e:pt
<!--TAGS-->
<!--tag:Effect:Particle-->
