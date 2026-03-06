# StringEquals

**タイプ**: 🟧 比較 (Compare)

## 説明

2つの文字列が等しいかどうかをチェックします。

> *Checks if value1 equals value2. Both values can use [variables](/Skills/Variables) and [placeholders](/Skills/Placeholders).*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `value1` | val1, v1, string, s | The first value |  |
| `value2` | val2, v2, value, val, v, equals, eq, e | The second value |  |

## 使用例

**例 1:**

```yaml
  Conditions:
  - stringequals{val1="yes!";val2="yes!"} true
```

**例 2:**

```yaml
  Conditions:
  - stringequals{val1="%denizen_<player[<trigger.uuid>].item_in_hand.has_nbt[special_item]>%";val2="true"} true
```

**例 3:**

```yaml
  Conditions:
  - stringequals{val1="%denizen_<player[<trigger.uuid>].item_in_hand.raw_nbt.get[mythic_type].after[string:]>%";val2="SomeMythicItem"} true
```

## エイリアス

- `stringEq`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/StringEquals)を基に日本語訳されています。
