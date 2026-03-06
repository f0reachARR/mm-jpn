# BlockWave（ブロックウェーブ）

## 説明

指定したブロックの波を、さまざまな形状・速度・ブロック種類で生成します。

このエフェクトは実際にはワールドのブロックを一切変更しないため、環境を破壊することはありません。変更は純粋に視覚的なものです。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| material | m | blockwave に使用する[マテリアル](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html) | （なし） |
| radius | r | blockwave エフェクトの範囲 | 2 |
| radiusy | ry | Y方向の範囲 | radius の値 |
| duration | d | エフェクトの継続時間（tick単位） | 15 |
| shape | s | エフェクトの形状（Sphere / Cube） | sphere |
| velocity | v | エフェクトの速度 | 0.2 |
| horizontalvelocity | velocityh, vh | 水平方向の速度 | 0 |
| specificvelocities | sv | `vx`・`vy`・`vz` 属性を使用するか | false |
| velocityx | vx | X軸方向の速度 | 0 |
| velocityy | vy | Y軸方向の速度 | 0 |
| velocityz | vz | Z軸方向の速度 | 0 |
| noise | n | エフェクトのノイズ量 | 0 |
| hidesourceblock | hidesource, hsb, hs | ソースブロックを非表示にするか | true |
| ignoreair | ia | 空気ブロックを無視するか | true |

### material 属性
material を空白にした場合、使用されたブロックの種類が自動的に使用されます。例えば、村の建物に使用した場合、建物のブロックがウェーブに使用されます。

## 使用例

```yaml
  Skills:
  - blockwave{duration=100;material=stone;radius=5;radiusY=5;velocity=10;shape=sphere} @selflocation
```
> セルフロケーションを起点に球体状の石のブロックウェーブを作成

## エイリアス
- [x] effect:blockWave
- [x] e:blockWave
