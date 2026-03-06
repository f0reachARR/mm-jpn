# biometype

**タイプ**: 🟩 ロケーション (Location)

## 説明

ロケーションのバイオームカテゴリをテストします。

> *Tests if the target is within the given list of biome types*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `type` | t | チェックするバイオームのリスト | ocean |
| `exact` | e | Whether to match the type exactly | true |

## 使用例

```yaml
Conditions:
- biometype{t=jungle,ocean,extreme_hills} true
```

## エイリアス

- `biomecategory`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/biometype)を基に日本語訳されています。
