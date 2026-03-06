# @BlocksNearOrigin (原点付近ブロックターゲッター)

## 概要
メタスキルの原点付近にあるすべてのブロックをターゲットにします。

- **タイプ**: 複数場所ターゲッター
- **省略形**: `@BNO`

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| radius | r | ターゲッターの半径（ブロック数） | 2 |
| radiusy | ry, yradius, yr | Y軸の半径（未指定の場合はradius） | radius |
| shape | s | 選択形状（`SPHERE` または `CUBE`） | SPHERE |
| noise | n | ターゲッターのランダム性 | 0 |
| noair | na | 空気ブロックをターゲットにしないか | true |
| onlyair | oa | 空気ブロックのみをターゲットにするか | false |

## 使用例
```yaml
ExampleSkill:
  Skills:
  # 原点から10ブロック以内のブロックにパーティクル（noise=0.5でランダム性を加える）
  - effect:particles @BlocksNearOrigin{r=10;noise=0.5}
```

## 備考
- `noise` 値を増やすとランダムに一部のブロックが除外されます
- ブロックを操作するメカニクス（`setblock`など）と組み合わせると強力です
