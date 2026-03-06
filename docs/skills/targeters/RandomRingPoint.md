# @RandomRingPoint (ランダムリングポイントターゲッター)

## 概要
キャスターを中心としたリング上のランダムな位置をターゲットにします。

- **タイプ**: 複数場所ターゲッター

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| radius | r | リングの半径（ブロック数） | 5 |
| points | p | 生成するポイントの総数 | 10 |
| amount | a | 実際にターゲットにするポイントの数 | 1 |
| rotationx | rotx, rx | X軸の回転 | 0 |
| rotationy | roty, ry | Y軸の回転 | 0 |
| rotationz | rotz, rz | Z軸の回転 | 0 |
| offsetx | offx, ox | X軸のオフセット | 0 |
| offsety | offy, oy | Y軸のオフセット | 0 |
| offsetz | offz, oz | Z軸のオフセット | 0 |

## 使用例
```yaml
ExampleSkill:
  Skills:
  - particle @randomRingPoint{r=4;p=20;a=10}  # 半径4の円上の20点から10点をランダムに選んでパーティクル
```

## 備考
- `points` でリング上の総分割数、`amount` でその中から選ぶ数を指定します
- ランダムな円形パターンの攻撃に適しています
