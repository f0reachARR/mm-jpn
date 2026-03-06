# MobsInRadius

**タイプ**: 🟩 ロケーション (Location)

## 説明

指定された半径内のMythicMobの数をチェックします。

> *Checks how many mobs are in a given radius*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `types` | type, t | The types of mobs to check for |  |
| `amount` | a | The range of mobs to check for. The caster is not counted | 1 |
| `radius` | r | The radius to check | 5 |

## 使用例

**例 1:**

```yaml
  Conditions:
  - mobsInRadius{types=NewZombie;amount=5to10;radius=15}
```

**例 2:**

```yaml
  Conditions:
  - mobsInRadius{types=NewZombie,NewSkeleton,NewSpider;amount=5to10;radius=15}
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/MobsInRadius)を基に日本語訳されています。
