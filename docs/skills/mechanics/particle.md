# Particle（パーティクル）

## 説明

ターゲットエンティティまたは位置にパーティクルエフェクトを生成します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| particle | p | 使用する[パーティクルタイプ] | reddust<!--type:Particle--> |
| mob | m, t | パーティクルとしてスポーンするエンティティ | <!--type:Mob--> |
| amount | count, a | 生成するパーティクル数 | 10 |
| spread | offset | パーティクルの広がり | 0 |
| hSpread | hs | パーティクルの水平方向の広がり | `spread` |
| vSpread | vs, yspread, ys | パーティクルの広がり | `spread` |
| xSpread | xs | パーティクルの広がり | hSpread |
| zSpread | zs | パーティクルの広がり | hSpread |
| speed | s | \1の名前 | 0 |
| yOffset | y | ターゲットからのパーティクルのYオフセット | 0 |
| viewDistance | vd | パーティクルが描画される距離 | 128 |
| fromorigin | fo | パーティクルをメカニックの原点から生成するか | false |
| directional | d | パーティクルが方向移動を使用するか | false |
| directionReversed | dr | パーティクルの方向を反転するか | false |
| direction | dir | パーティクルの移動方向ベクトル | 0,0,0 (x,y,z) |
| fixedyaw | yaw | メカニックのロケーションターゲットのヨーを設定 | -1111 |
| fixedpitch | pitch | メカニックのロケーションターゲットのピッチを設定 | -1111 |
| audience |  | パーティクルエフェクトの[オーディエンス] | nearby<!--type:Audience--> |
| color | c | パーティクルの色（対応している場合） | <!--type:Color--> |
| exactoffsets | eo | パーティクルのランダムスポーン位置を計算する数式を変更するか | false |

### Entity-Only Attributes

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| useEyeLocation | uel | (true/false) Whether to base the particles on the entity's eyes | false |
| forwardOffset | startfoffset, sfo | ターゲットエンティティからの前方オフセット | 0 |
| sideOffset | soffset, sso | ターゲットエンティティからの側面オフセット | 0 |

## エイリアス

- [x] effect:particles
- [x] effect:particle
- [x] particles
- [x] particle
- [x] e:particles
- [x] e:particle
- [x] e:p
<!-- LINKS -->
[particle type]: /Skills/Mechanics/Particle/Particle-Types
[particle types wiki page]: /Skills/Mechanics/Particle/Particle-Types
<!--TAGS-->
<!--tag:Effect:Particle-->
