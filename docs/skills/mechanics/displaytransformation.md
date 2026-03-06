# DisplayTransformation（ディスプレイ変換）

## 説明

ターゲットのディスプレイエンティティのトランスフォーメーション（変換）を設定します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| translationx | tx | X軸方向の移動量 | 0 |
| translationy | ty | Y軸方向の移動量 | 0 |
| translationz | tz | Z軸方向の移動量 | 0 |
| scalex | sx | X軸方向のスケール | 1 |
| scaley | sy | Y軸方向のスケール | 1 |
| scalez | sz | Z軸方向のスケール | 1 |
| duration | d | 変換の継続時間（tick単位） | 0 |
| interpolation | interp, i | 補間時間（tick単位） | 0 |

## 使用例

```yaml
  Skills:
  - displaytransformation{sx=2;sy=2;sz=2;d=20} @target ~onTimer:20
```

## エイリアス
- [x] dt
- [x] disptransform
