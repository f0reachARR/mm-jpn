# entitytype

**タイプ**: 🟦 エンティティ (Entity)

## 説明

ターゲットのエンティティタイプをテストします。

> *Tests if the entity type of the target is the specified one.  
A list of valid entity types can be found on the [Spigot Javadocs](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/entity/EntityType.html).*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `type` | types, t | A list of entity types to match |  |

## 使用例

**例 1:**

```yaml
Conditions:
- entitytype{t=ZOMBIE} true
```

**例 2:**

```yaml
TargetConditions:
- entitytype{t=WITCH} true
```

**例 3:**

```yaml
TriggerConditions:
- entitytype{t=PLAYER} true
```

## エイリアス

- `mobtype`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/entitytype)を基に日本語訳されています。
