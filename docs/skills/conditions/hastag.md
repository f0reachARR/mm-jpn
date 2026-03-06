# hastag

**タイプ**: 🟦 エンティティ (Entity)

## 説明

ターゲットがスコアボードタグを持っているかどうかをテストします。

> *Tests if the target has a scoreboard tag*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `tag` | t | The tag to check for |  |

## 使用例

**例 1:**

```yaml
  Conditions:
  - hastag{t=KilledBoss1} true
```

**例 2:**

```yaml
  TargetConditions:
  - hastag{t=PuzzleRoom1Solved} true
```

## エイリアス

- `hasScoreboardTag`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/hastag)を基に日本語訳されています。
