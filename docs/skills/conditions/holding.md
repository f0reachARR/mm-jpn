# holding

**タイプ**: 🟦 エンティティ (Entity)

## 説明

ターゲットプレイヤーがアイテムを手に持っているかどうかをテストします。

> *Checks if the target is holding a given material.  
Uses the [Item Matcher](/Items/Item-Matcher)*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `material` | m, type, t, item, i, mat, types | A material, MythicItem or MMOItems internal id to check for |  |
| `strict` | exact, e | Whether the matcher should more strictly match the target item | false |
| `vanillaonly` | vanilla | Whether the matched item can only be a vanilla one | false |

## 使用例

**例 1:**

```yaml
# Make sure you use all caps for materials, otherwise the console will say it is not a valid material!
Conditions:
- holding{m=DIAMOND_SWORD} true
```

**例 2:**

```yaml
Conditions:
- holding{m=mmoitems.TOOL.PICKAXE_5} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/holding)を基に日本語訳されています。
