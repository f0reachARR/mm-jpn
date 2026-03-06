# BoundingBoxesOverlap

**タイプ**: 🟦 エンティティ (Entity)

## 説明

2つのエンティティのバウンディングボックスが重なっているかどうかをチェックします。

> *Checks if the caster's BoundingBox overlaps with the target's*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `shiftforward` | so, forwardoffset, fo, forward, f | The forward offset of the caster's BoundingBox | 0.0 |

## 使用例

```yaml
  TargetConditions:
  - boundingBoxesOverlap false
```

## エイリアス

- `bbsoverlap`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/BoundingBoxesOverlap)を基に日本語訳されています。
