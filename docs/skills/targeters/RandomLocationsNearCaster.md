# @RandomLocationsNearCaster (キャスター付近ランダム位置ターゲッター)

## 概要
キャスターの近くのランダムな位置をターゲットにします。

- **タイプ**: 複数場所ターゲッター
- **省略形**: `@randomLocations`, `@RLNC`

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| amount | a | ポイントの数 | 5 |
| radius | r, maxradius, maxr | ポイントが生成される最大半径 | 5 |
| minradius | minr | ポイントが生成される最小半径 | 0 |
| spacing | s | 選択されたターゲット間の最小距離 | 0 |
| onSurface | onsurf, os | 固体ブロックの上の位置のみをターゲットにするか | false |

## 使用例
```yaml
ExampleSkill:
  Skills:
  - effect:particles @RandomLocationsNearCaster{a=5;r=2}  # キャスター付近の半径2ブロック内に5か所ランダム位置
```

## 備考
- `minradius` でキャスターに近すぎる位置を除外できます
- `onSurface=true` でブロックの上面のみを対象にします
- `@RandomLocationsNearOrigin` はスキルの原点基準版です
