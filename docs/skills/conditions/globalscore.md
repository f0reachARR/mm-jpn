# globalscore

**タイプ**: 🟥 メタ (Meta)

## 説明

グローバルスコアボードの値をチェックします。

> *Checks a global scoreboard value (the value associated with the fake player __GLOBAL__)*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `objective` | obj, o | The objective |  |
| `value` | val, v | The value to match |  |

## 使用例

```yaml
  Conditions:
  - globalscore{o=KillCount;value=5} true
```

## エイリアス

- `scoreglobal`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/globalscore)を基に日本語訳されています。
