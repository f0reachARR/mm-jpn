# HasEnchantment

**タイプ**: 🟦 エンティティ (Entity)

## 説明

ターゲットのアイテムが指定されたエンチャントを持っているかどうかをチェックします。

> *Checks if the target entity's equipped item has an enchantment. A list of valid enchantments can be found in the [Spigot Javadoc](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/enchantments/Enchantment.html).*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `enchantment` | type, ench, e, t | The enchantment to test for | ANY |
| `level` | lvl, l | The level to test for | >0 |

## 使用例

```yaml
  TargetConditions:
  - hasenchantment{e=DAMAGE_ALL;l=>3} true
```

## エイリアス

- `hasEnchant`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/HasEnchantment)を基に日本語訳されています。
