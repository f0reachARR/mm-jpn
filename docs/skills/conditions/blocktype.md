# blocktype

**タイプ**: 🟩 ロケーション (Location)

## 説明

ターゲットロケーションに存在するマテリアルタイプをテストします。

> *This condition tests if material type present at the target location is the specified one.  
Valid for any [Spigot material type](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html), wildcards and block tags.*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `types` | type, t, material, mat, m, block, b | A list of materials or MMOItem's block name to check. Does also support wildcards and block tags | DIRT |

## 使用例

**例 1:**

```yaml
  Conditions:
  - blocktype{type=dirt} true
```

**例 2:**

```yaml
  Conditions:
  - blockType{type=#leaves,*_log,redstone_torch[lit=true]}
```

## エイリアス

- `inblock`
- `insideblock`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/blocktype)を基に日本語訳されています。
