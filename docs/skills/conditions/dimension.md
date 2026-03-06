# dimension

**タイプ**: 🟩 ロケーション (Location)

## 説明

エンティティがいるディメンションをチェックします。

> *Checks if the target is within a certain dimension.  
A list of valid dimensions can be found in the [Spigot Enviroment javadoc](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/World.Environment.html).*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `dimension` | d, environment, env | A list of dimensions to check | THE_END |

## 使用例

```yaml
  Conditions:
  - dimension{d=NORMAL} true
```

## エイリアス

- `environment`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/dimension)を基に日本語訳されています。
