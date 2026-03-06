# cuboid

**タイプ**: 🟩 ロケーション (Location)

## 説明

ターゲットが直方体領域内にいるかどうかをチェックします。

> *Whether the target is within a cuboid that has `location1` and `location2` as opposite vertices*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `location1` | loc1, l1, a | x,y,z coordinates for the 1st point. |  |
| `location2` | loc2, l2, b | x,y,z coordinates for the 2nd point. |  |
| `relative` | r | Whether or not the coordinates should be relative to the caster | false |

## 使用例

```yaml
  TargetConditions:
  - cuboid{location1=x,y,z;location2=x,y,z;relative=true}
```

## エイリアス

- `incuboid`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/cuboid)を基に日本語訳されています。
