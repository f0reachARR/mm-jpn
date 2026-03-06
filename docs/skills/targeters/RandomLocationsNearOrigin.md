# @RandomLocationsNearOrigin (原点付近ランダム位置ターゲッター)

## 概要
メタスキルの原点付近のランダムな位置をターゲットにします。

- **タイプ**: 複数場所ターゲッター
- **省略形**: `@RLO`, `@randomLocationsOrigin`, `@RLNO`

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
  - projectile{...;
    onEnd=[
      - effect:particles @RandomLocationsNearOrigin{a=10;r=4;minr=1}
      # プロジェクタイル終了時、原点付近の半径1〜4ブロック内に10か所ランダム位置にパーティクル
    ]}
```

## 備考
- `@RandomLocationsNearCaster` はキャスター基準、こちらはスキルの原点基準です
- プロジェクタイルの着弾エフェクトに最適です
