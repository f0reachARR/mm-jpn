# DistanceFromLocation

**タイプ**: 🟩 ロケーション (Location)

## 説明

指定されたロケーションからの距離をチェックします。

> *Whether the distance between the target and a specified location is within a certain range*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `x` |  | The x component of the location | 0 |
| `y` |  | The y component of the location | 0 |
| `z` |  | The z component of the location | 0 |
| `world` | w | The world of the location. Defaults to the world of the target |  |
| `distance` | d | The distance from the specified location to check against |  |

## 使用例

```yaml
  TargetConditions:
  - distanceFromLocation{x=10;y=20;z=30;distance=<20} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/DistanceFromLocation)を基に日本語訳されています。
