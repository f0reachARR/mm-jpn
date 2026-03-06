# playernotwithin

**タイプ**: 🟧 比較 (Compare)

## 説明

指定された半径内にプレイヤーがいないかどうかをチェックします。

> *Checks if any players are within a radius of the target.*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `distance` | d | The radius to check in | 0 |

## 使用例

```yaml
  Conditions:
  - playernotwithin{d=10} true
```

## エイリアス

- `playersnotwithin`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/playernotwithin)を基に日本語訳されています。
