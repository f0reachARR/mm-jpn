# EnderDragonSetPhase（エンダードラゴンフェーズ設定）

## 説明

エンダードラゴンのフェーズを設定します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| phase | p | 設定するフェーズ。使用可能なフェーズ一覧を参照 | HOLDING_PATTERN |

### 使用可能なフェーズ
- `CIRCLING`
- `STRAFING`
- `FLY_TO_PORTAL`
- `LAND_ON_PORTAL`
- `LEAVE_PORTAL`
- `BREATH_ATTACK`
- `SEARCH_FOR_BREATH_ATTACK_TARGET`
- `ROAR_BEFORE_ATTACK`
- `CHARGE_PLAYER`
- `DYING`
- `HOVER`
- `HOLDING_PATTERN`（デフォルト）

## 使用例

```yaml
  Skills:
  - enderdragonsetphase{phase=BREATH_ATTACK} @self ~onDamaged
```

## エイリアス
- [x] edsp
- [x] setdragonphase
