# モブファクション (Mob Factions)

ファクションを使用すると、モブをグループに割り当てることができます。これはカスタムAI設定やターゲッターフィルタリングと連携して、異なるファクションのモブと戦ったり、プレイヤーを助けたりするモブを作ることができます。

## 基本的な使用方法

```yaml
ExampleMob:
  Type: zombie
  Faction: ゾンビ軍団
```

> ファクションは大文字小文字を区別するため、ファクション条件を使用する際は注意してください。

## AI設定でのファクションの使用

### 特定のファクションに対してのみ敵対的なモブ

```yaml
# ゾンビ軍団ファクションのモブ
ZombieWarrior:
  Type: zombie
  Faction: ゾンビ軍団
  AIGoalSelectors:
  - clear
  - meleeattack
  AITargetSelectors:
  - clear
  - SpecificFaction:スケルトン軍団  # スケルトン軍団のモブをターゲット

# スケルトン軍団ファクションのモブ  
SkeletonWarrior:
  Type: skeleton
  Faction: スケルトン軍団
  AIGoalSelectors:
  - clear
  - meleeattack
  AITargetSelectors:
  - clear
  - SpecificFaction:ゾンビ軍団  # ゾンビ軍団のモブをターゲット
```

### ファクションから逃げるモブ

```yaml
FriendlyMob:
  Type: villager
  AIGoalSelectors:
  - clear
  - fleefaction:ゾンビ軍団  # ゾンビ軍団ファクションのモブから逃げる
```

## コンディションでのファクションの使用

ファクションはスキルコンディションでも使用できます：

```yaml
MySkill:
  TargetConditions:
  - faction{f=ゾンビ軍団}  # ターゲットがゾンビ軍団ファクションの場合のみ
```

## ファクションターゲッター

スキルのターゲッターでもファクションを使用できます：

```yaml
Skills:
- damage{amount=20} @PlayersInRadius{r=10;faction=敵ファクション}
```

## 例：敵対するファクション

```yaml
# 守護騎士ファクション（プレイヤーを守る）
GuardKnight:
  Type: IRON_GOLEM
  Display: '&7守護騎士'
  Faction: 守護軍
  AIGoalSelectors:
  - clear
  - meleeattack
  AITargetSelectors:
  - clear
  - SpecificFaction:ダークアーミー

# ダーク軍ファクション（プレイヤーを攻撃）
DarkSoldier:
  Type: ZOMBIE
  Display: '&8ダーク兵士'
  Faction: ダークアーミー
  AIGoalSelectors:
  - clear
  - meleeattack
  AITargetSelectors:
  - clear
  - players
  - SpecificFaction:守護軍
```
