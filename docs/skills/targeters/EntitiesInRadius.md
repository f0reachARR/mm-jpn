# @EntitiesInRadius (半径内エンティティターゲッター)

## 概要
キャスターを中心とした指定半径内のすべてのエンティティをターゲットにします。

- **タイプ**: 複数エンティティターゲッター
- **省略形**: `@livingInRadius`, `@EIR`, `@livingEntitiesInRadius`, `@allInRadius`, `@entitiesnearby`, `@nearbyentities`

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| shape | | エンティティを取得する形状（[Shape](/Enum/Shape)参照） | SPHERE |
| livingonly | living, l | 生きているエンティティのみをターゲットにするか | true |

## 使用例
```yaml
ExampleSkill:
  Skills:
  - ignite @EIR{r=10}  # 半径10ブロック内のすべてのエンティティに火をつける
```

## 備考
- 半径（`r`）は多くのターゲッターと共通する属性です
- `livingonly=false` で非生物エンティティもターゲットにできます
