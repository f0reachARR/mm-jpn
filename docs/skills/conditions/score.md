# score

**タイプ**: 🟦 エンティティ (Entity)

## 説明

スコアボードの値をチェックします。

> *Checks a scoreboard value of the target entity.*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `objective` | obj, o | The objective |  |
| `entry` | ent, e | The entry |  |
| `value` | val, v | The value to match |  |

## 使用例

```yaml
  Conditions:
  - score{o=PlayerKills;e=Akim91;v=10} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/score)を基に日本語訳されています。
