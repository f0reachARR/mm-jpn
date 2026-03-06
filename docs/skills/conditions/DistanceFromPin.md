# DistanceFromPin

**タイプ**: 🟩 ロケーション (Location)

## 説明

ピンからの距離をチェックします。

> *Checks if the target is within a certain distance of a specified [pin]*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `pin` | p | The pin to check against |  |
| `distance` | d | The distance to check against. Can be a range. |  |

## 使用例

```yaml
  Conditions:
  - distanceFromPin{pin=example_pin;d=>10} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/DistanceFromPin)を基に日本語訳されています。
