# DamageCause

**タイプ**: 🟦 エンティティ (Entity)

## 説明

ダメージの原因をチェックします。

> *Checks the cause of the damage the entity took, if the skilltree originated from a [onDamaged Trigger](/Skills/Triggers/onDamaged) or an [onDamaged Aura](/skills/mechanics/ondamaged).  
A list of valid damage causes can be found in the [Spigot DamageCause javadoc](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityDamageEvent.DamageCause.html).*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `damagecause` | cause, c | The damage cause to match | ENTITY_ATTACK |

## 使用例

```yaml
  Conditions:
  - damagecause{cause=ENTITY_ATTACK} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/DamageCause)を基に日本語訳されています。
