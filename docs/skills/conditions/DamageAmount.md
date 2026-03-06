# DamageAmount

**タイプ**: 🟦 エンティティ (Entity)

## 説明

エンティティが受けたダメージの範囲をチェックします。

> *Checks for a range of damage the entity took, if the skilltree originated from a [onDamaged Trigger](/Skills/Triggers/onDamaged) or an [onDamaged Aura](/skills/mechanics/ondamaged).*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `damageAmount` | amount, a | Range of damage to check for | >0 |

## 使用例

```yaml
  Conditions:
  - damageamount{amount=>10} true
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/DamageAmount)を基に日本語訳されています。
