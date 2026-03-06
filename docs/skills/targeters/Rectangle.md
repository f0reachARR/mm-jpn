# @Rectangle (矩形・直方体形状位置ターゲッター)

## 概要
矩形（長方形）または直方体を構成するポイントの位置をターゲットにします。塗りつぶしの有無、輪郭のみ表示など様々なパラメーターで調整できます。

- **タイプ**: 複数場所ターゲッター
- **省略形**: `@cube`, `@cuboid`

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| x | | X軸のサイズ | 1 |
| y | | Y軸のサイズ | 1 |
| z | | Z軸のサイズ | 1 |
| xOffset | | X軸のオフセット | 0 |
| yOffset | | Y軸のオフセット | 0 |
| zOffset | | Z軸のオフセット | 0 |
| points | p, density, d | キューブの1辺あたりのポイント数 | 10 |
| filled | fill, f | 内部を塗りつぶすか | false |
| outline | edge, onlyEdge, e, onlyOutline, o | 輪郭のみ描画するか | false |
| rotation | r | 3D回転（x,y,z形式） | 0,0,0 |
| fromOrigin | origin | スキルの原点から描画するか | false |

## 使用例
```yaml
ExampleMob1:
  Type: ZOMBIE
  Skills:
  # ダメージを受けたとき、45度回転した矩形の輪郭にフレームパーティクル
  - particle{p=FLAME;a=1} @Rectangle{d=12;f=false;r=45,45,0;yOffset=1.5;outline=true} ~onDamaged

ExampleMob2:
  Type: ZOMBIE
  Skills:
  # ダメージを受けたとき、45,45,45度回転した塗りつぶし直方体にパーティクル
  - particle{p=SOUL_FIRE_FLAME;a=1} @Rectangle{d=12;r=45,45,45;yOffset=3;fill=true} ~onDamaged
```

## 備考
- `filled=true` と `outline=true` を組み合わせることで外枠のみ+塗りつぶしも可能です
- `rotation` は `x,y,z` 形式で3軸の回転角度を度数で指定します
