# EnderDragonSetRespawnPhase（エンダードラゴン復活フェーズ設定）

## 説明

エンダードラゴンの復活フェーズを設定します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| phase | p | 復活フェーズ。使用可能な値を参照 | START |

### 使用可能な復活フェーズ
- `START`
- `PREPARING_TO_SUMMON_PILLARS`
- `SUMMONING_PILLARS`
- `SUMMONING_DRAGON`
- `END`
- `NONE`

## 使用例

```yaml
  Skills:
  - enderdragonsetrespawnphase{phase=SUMMONING_DRAGON} @self ~onSpawn
```

## エイリアス
- [x] edsrp
- [x] setdragonrespawnphase
