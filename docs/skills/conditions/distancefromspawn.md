# distancefromspawn

**タイプ**: 🟩 ロケーション (Location)

## 説明

スポーン地点からの距離をチェックします。

> *Whether the distance from the world's spawn point to the target is within the given range*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `distance` | d | 一致させる距離 |  |

## 使用例

**例 1:**

```yaml
  Conditions:
  - distancefromspawn{d=<100} true
```

**例 2:**

```yaml
  Conditions:
  - distancefromspawn{d=>50} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/distancefromspawn)を基に日本語訳されています。
