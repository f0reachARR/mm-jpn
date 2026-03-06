# EnderDragonPhase

**タイプ**: 🟦 エンティティ (Entity)

## 説明

エンダードラゴンのフェーズをチェックします。

> *Checks the phase of the target Ender Dragon entity.  
A list of valid phases can be found in the [Spigot Phase javadoc](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/entity/EnderDragon.Phase.html).*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `phase` | p | A list of phases to match |  |

## 使用例

**例 1:**

```yaml
  Conditions:
  - enderdragonphase{phase=CIRCLING} true
```

**例 2:**

```yaml
Conditions:
- enderdragonphase{phases=FLY_TO_PORTAL,LEAVE_PORTAL} true
```

## エイリアス

- `edragonPhase`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/EnderDragonPhase)を基に日本語訳されています。
