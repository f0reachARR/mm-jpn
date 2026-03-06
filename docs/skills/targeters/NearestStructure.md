# @NearestStructure (最近傍構造物ターゲッター)

## 概要
キャスターのワールドで指定した半径内にある最も近い構造物の位置をターゲットにします。

- **タイプ**: 単一場所ターゲッター

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| type | t | 構造物のタイプ | STRONGHOLD |
| radius | r | ターゲッターの半径 | 5000 |
| unexplored | u | 未探索の構造物のみを対象にするか | false |

## 使用例
```yaml
StrongholdFinder:
  Cooldown: 10
  Skills:
  # 最寄りの要塞に向けてパーティクルのプロジェクタイルを発射
  - projectile{hp=false;se=false;sb=false;v=5;d=100;onTick=[ effect:particles ]} @NearestStructure{r=1000}
```

## 備考
- Minecraftのバニラ構造物（STRONGHOLD, VILLAGE, NEFORTRESSなど）を指定できます
- 大きな半径を指定するとパフォーマンスに影響する場合があります
