# hasItem

**タイプ**: 🟦 エンティティ (Entity)

## 説明

ターゲットプレイヤーが指定されたアイテムを持っているかどうかをチェックします。

> *Tests if the target player or an item container has exactly the given number of the given material.  
Uses the [Item Matcher](/Items/Item-Matcher)*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `item` | i, material, m, type, t, mat, types | The item to check for | DIRT |
| `amount` | a | The amount to check for | >0 |
| `strict` | exact, e | Whether the matcher should more strictly match the target item | false |
| `vanillaonly` | vanilla | Whether the matched item can only be a vanilla one | false |

## 使用例

**例 1:**

```yaml
  Conditions:
  - hasitem{i=stick;amount=>1} true
```

**例 2:**

```yaml
  Conditions:
  - hasitem{i=my_custom_item;amount=<10} true
```

**例 3:**

```yaml
  Conditions:
  - hasitem{i=mmoitems.SWORD.CUTLASS;amount=1to10} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/hasItem)を基に日本語訳されています。
