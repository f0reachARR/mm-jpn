# hascurrency

**タイプ**: 🟦 エンティティ (Entity)

## 説明

ターゲットが指定された通貨を持っているかどうかをチェックします。

> *If the target has the given amount of vault currency*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `amount` | a | The amount of currency |  |

## 使用例

```yaml
  Conditions:
  - hascurrency{a=1000} true
```

## エイリアス

- `hasmoney`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/hascurrency)を基に日本語訳されています。
