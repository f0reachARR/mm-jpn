# owner

**タイプ**: 🟦 エンティティ (Entity)

## 説明

エンティティのオーナーをチェックします。

> *Checks if the target entity is the owner of the caster. 

- If the caster is a tamable mob, if will check if the target entity is the mob's "vanilla" owner
- If the caster is not a tamable mob, then to match the target entity must have been set as the owner via the [SetOwner](/skills/mechanics/setowner) mechanic*

## 使用例

```yaml
  TargetConditions:
  - owner true
```

## エイリアス

- `isOwner`

---

> このページは[MythicMobs公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Skills/Conditions/owner)を基に日本語訳されています。
