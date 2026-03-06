# ParticleOrbital（パーティクル軌道）

## 説明

ターゲットの周囲にパーティクルの軌道を描きます。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| radius | r | ターゲット周囲の半径 | 4 |
| points | p | How many points make up the circle | 20 |
| ticks | t | For how many ticks this effect will last | 100 |
| interval | in, i | Tick speed at which the particle moves (faster tick rate=slower movement) | 10 |
| rotationX | rotX, rX | Rotates the orbit around the X axis | 0 |
| rotationY | rotY, rY | Rotates the orbit around the Y axis | 0 |
| rotationZ | rotZ, rZ | Rotates the orbit around the Z axis | 0 |
| offsetX | offx, ox | \1の名前 | 0 |
| offsetY | offy, oy | \1の名前 | 0 |
| offsetZ | offz, oz | \1の名前 | 0 |
| angularVelocityX | avx, vx | Modifies the angular velocity around the X axis | 0 |
| angularVelocityY | avy, vy | Modifies the angular velocity around the Y axis | 0 |
| angularVelocityZ | avz, vz | Modifies the angular velocity around the Z axis | 0 |
| rotate |  | Whether the particles should rotate. Defaults to true if one of the angularvelocity attributes is greater than 0 |  |
| reversed | reverse | Whether the particles should orbit in the opposite direction | false |

## エイリアス

- [x] effect:particleorbital
- [x] e:particleorbital
- [x] effect:particlecircle
- [x] particlecircle
- [x] e:particlecricle
<!--TAGS-->
<!--tag:Effect:Particle-->
