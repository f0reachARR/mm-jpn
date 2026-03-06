# fallspeed

**タイプ**: 🟦 エンティティ (Entity)

## 説明

エンティティの落下速度をチェックします。

> *If the fall speed of the target is within the given range*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `speed` | s | The velocity to match |  |

## 使用例

```yaml
  Conditions:
  - fallspeed{s=>5} true
```

## エイリアス

- `fallingspeed`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/fallspeed)を基に日本語訳されています。
