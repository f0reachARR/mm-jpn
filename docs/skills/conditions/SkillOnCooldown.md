# SkillOnCooldown

**タイプ**: 🟦 エンティティ (Entity)

## 説明

指定されたスキルがクールダウン中かどうかをチェックします。

> *Checks if the given skill is in cooldown for the target entity*

## 属性

| 属性 | エイリアス | 説明 | デフォルト |
|------|-----------|------|-----------|
| `skill` | s | The metaskill to check |  |

## 使用例

```yaml
  TargetConditions:
  - skillOnCooldown{skill=TestSkill}
```

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/SkillOnCooldown)を基に日本語訳されています。
