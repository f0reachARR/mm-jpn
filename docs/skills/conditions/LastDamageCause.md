# LastDamageCause

**タイプ**: 🟦 エンティティ (Entity)

## 説明

最後のダメージの原因をチェックします。

> *Checks the target's last damage cause.  
You can find a list of valid damage causes on the [Spigot Javadoc](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/event/entity/EntityDamageEvent.DamageCause.html)*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `damagecause` | cause, c | The damage cause to match | ENTITY_ATTACK |

## 使用例

```yaml
  Conditions:
  - lastdamagecause{c=ENTITY_ATTACK} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/LastDamageCause)を基に日本語訳されています。
