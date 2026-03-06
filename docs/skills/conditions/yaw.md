# yaw

**タイプ**: 🟦 エンティティ (Entity)

## 説明

エンティティのヨー（左右の向き）をチェックします。

> *Checks the yaw of the target entity against a range.*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `yaw` | y | The yaw to check for | 0 |
| `clamp` | c | Whether to clamp yaw to a value in a 0-360 range | true |

## 使用例

**例 1:**

```yaml
  Conditions:
  - yaw{y=90to180} true
```

**例 2:**

```yaml
  Conditions:
  - yaw{y=>0} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/yaw)を基に日本語訳されています。
