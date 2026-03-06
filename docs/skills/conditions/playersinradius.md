# playersinradius

**タイプ**: 🟩 ロケーション (Location)

## 説明

指定された半径内のプレイヤー数をチェックします。

> *Checks how many players are in a radius.*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `amount` | a | The given range value to check | >0 |
| `radius` | r, distance, d | The given radius to check | 32 |
| `ignorespectator` | is | Whether players in spectator mode should be ignored | true |

## 使用例

```yaml
  Conditions:
  - playersinradius{a=>3;r=16}
```

## エイリアス

- `pir`
- `playerInRadius`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/playersinradius)を基に日本語訳されています。
