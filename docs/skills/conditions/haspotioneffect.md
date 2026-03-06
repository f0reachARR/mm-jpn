# haspotioneffect

**タイプ**: 🟦 エンティティ (Entity)

## 説明

ターゲットエンティティがポーション効果を持っているかどうかをテストします。

> *Tests if the target entity has a potion effect*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `type` | t | The potion effect type | ANY |
| `level` | lvl, l | An optional level range to match |  |
| `duration` | d | An optional duration range to match |  |

## 使用例

**例 1:**

```yaml
  Conditions:
  - haspotioneffect{t=SLOW;l=0-2;d=0-9999} true
```

**例 2:**

```yaml
  TargetConditions:
  - haspotioneffect{t=Speed;l=0-9} true
```

## エイリアス

- `hasPotion`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/haspotioneffect)を基に日本語訳されています。
