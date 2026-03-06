# haspermission

**タイプ**: 🟦 エンティティ (Entity)

## 説明

ターゲットプレイヤーが指定されたパーミッションを持っているかどうかをテストします。

> *This condition checks if the target player has a permission.*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `permission` | p | The permission to check for. |  |

## 使用例

**例 1:**

```yaml
  Conditions:
  - haspermission{p=permission.node.here} true
```

**例 2:**

```yaml
  TargetConditions:
  - haspermission{p=permission.node.here} true
```

**例 3:**

```yaml
  TriggerConditions:
  - haspermission{p=permission.node.here} true
```

## エイリアス

- `permission`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/haspermission)を基に日本語訳されています。
