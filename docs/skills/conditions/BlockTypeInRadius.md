# BlockTypeInRadius

**タイプ**: 🟩 ロケーション (Location)

## 説明

評価されたロケーション周辺の半径内にある指定されたブロックの量をチェックします。

> *Checks against the amount of specified blocks in a radius around the evaluated location.*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `types` | type, t, material, mat, m, b, block | チェックするマテリアルのリスト | DIRT |
| `radius` | r | 半径 | 8 |
| `amount` | a | 一致させるブロックの数 | >0 |

## 使用例

```yaml
  TargetConditions:
  - blockTypeInRadius{type=STONE;amount=>10;radius=3} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/BlockTypeInRadius)を基に日本語訳されています。
