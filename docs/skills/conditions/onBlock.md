# onBlock

**タイプ**: 🟩 ロケーション (Location)

## 説明

エンティティが特定のブロックの上にいるかどうかをチェックします。

> *Matches the block the target entity is standing on.  
A list of available materials can be found on the [Spigot Javadoc](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `material` | types, type, t, mat, m, block, b | A list of materials. The condition will match if one is found. Does also support wildcards and block tags | STONE |

## 使用例

**例 1:**

```yaml
  TargetConditions:
  - onblock{m=BEDROCK,OAK_LEAVES,ACACIA_FENCE} false
```

**例 2:**

```yaml
  TargetConditions:
  - onblock{m=DIRT,STONE,GRAVEL} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/onBlock)を基に日本語訳されています。
