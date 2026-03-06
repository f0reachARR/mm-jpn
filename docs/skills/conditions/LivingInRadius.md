# LivingInRadius

**タイプ**: 🟩 ロケーション (Location)

## 説明

指定された半径内の生きているエンティティの数をチェックします。

> *Matches a range to how many living entities are in the given radius*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `amount` | a | The amount to check for | 1 |
| `radius` | r | The radius of the search | 5 |

## 使用例

```yaml
  Conditions:
  - livinginradius{a=<5;r=10} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/LivingInRadius)を基に日本語訳されています。
