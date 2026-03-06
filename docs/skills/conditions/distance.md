# distance

**タイプ**: 🟧 比較 (Compare)

## 説明

キャスターとターゲット間の距離が指定範囲内かどうかをチェックします。

> *Whether the distance between the caster and target is within the given range.  
Can be a single number, a ranged value (20to40), or >10 <5, etc.*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `distance` | d | 一致させる距離 |  |

## 使用例

```yaml
  TargetConditions:
  - distance{d=<2}
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/distance)を基に日本語訳されています。
