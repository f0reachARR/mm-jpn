# CompareValues

**タイプ**: 🟧 比較 (Compare)

## 説明

指定された操作に基づいて2つの値を比較します。

> *Compares two values based on a specified operation.  
The comparison is made from `value1` against `value2`: This means that, for instance, in the `>` operation, it will return `true` if `value1` is greater than `value2`.  

This condition can compare Integers, Floats, Doubles (as usual) and Strings (lexicographically).  

The condition will try to "deduce" the type of values been given and compare the most stringent type first, gradually trying more loose comparisons if the previous one was not applicable (Integer --> Double --> String)

If you already know the type of values that will be passed, you can specify so via the `type` attribute, and only that specific comparison will be made, without wasting time in trials and errors. If the comparison cannot still be made because of value casting issues, the condition will return false*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `value1` | val1, v1 | The first value of the comparison |  |
| `value2` | val2, v2 | The second value of the comparison |  |
| `operator` | op | The [operator](#operator-attribute) to use | EQUALS |
| `type` | t | The (optional) type of the comparison. If not set, will try every available type from more stringent to less stringent. If set, the comparison will only happen assuming the values are of the specified type. Accepts any [Variable Type](/Skills/Variables#variable-types) |  |

## 使用例

```yaml
  Conditions:
  - comparevalues{value1=%server_online%;operator=>=;value2=1/3*%bungee_total%}
```

## エイリアス

- `comparevalue`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/CompareValues)を基に日本語訳されています。
