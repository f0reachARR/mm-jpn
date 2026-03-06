# モブの派閥 (Mob Factions)

派閥（Faction）システムを使うと、モブ同士の敵味方関係を定義できます。

---

## 概要

MythicMobs の派閥システムにより：
- 同じ派閥のモブは互いを攻撃しない
- 異なる派閥のモブは互いに攻撃し合える
- 派閥を使ってAIターゲットを制御できる

---

## 基本設定

```yaml
ZombieWarrior:
  Type: ZOMBIE
  Display: "ゾンビ戦士"
  Faction: Undead

SkeletonArcher:
  Type: SKELETON
  Display: "スケルトン弓兵"
  Faction: Undead

HumanGuard:
  Type: VILLAGER
  Display: "人間の衛兵"
  Faction: Human
```

上記の例では、`ZombieWarrior` と `SkeletonArcher` は同じ `Undead` 派閥のため互いを攻撃しません。`HumanGuard` は異なる `Human` 派閥のため、`Undead` のモブと戦います。

---

## AITargetSelectors での派閥使用

```yaml
ZombieWarrior:
  Type: ZOMBIE
  Faction: Undead
  AITargetSelectors:
  - 0 clear
  - 1 players
  - 2 faction{f=Human}          # Human 派閥を攻撃
  - 3 notfaction{f=Undead}       # Undead 以外を攻撃
```

### 派閥関連のAIターゲット

| セレクター | 説明 |
|-----------|------|
| `faction{f=<派閥名>}` | 指定した派閥のモブをターゲット |
| `notfaction{f=<派閥名>}` | 指定した派閥以外をターゲット |
| `samefaction` | 同じ派閥をターゲット（通常は非推奨） |

---

## 条件での派閥使用

スキル条件でも派閥を参照できます：

```yaml
Skills:
- skill{s=HealAllies} ~onTimer:100 ?targetFaction{f=Undead}
```

---

## 注意事項

- 派閥名は大文字・小文字を区別します（`undead` と `Undead` は別扱い）。
- デフォルトでは、派閥を設定していないモブはバニラの敵対関係に従います。
- プレイヤーは通常、どの派閥にも属しません（別途プラグインで設定可能）。

---

## 設定例：派閥間の戦争

```yaml
# Undead 派閥
SkeletonKnight:
  Type: SKELETON
  Display: "&7スケルトン騎士"
  Health: 100
  Damage: 10
  Faction: Undead
  AITargetSelectors:
  - 0 clear
  - 1 players
  - 2 faction{f=Holy}

# Holy 派閥
PaladinGuard:
  Type: VILLAGER
  Display: "&ePaladin の守護者"
  Health: 80
  Damage: 8
  Faction: Holy
  AITargetSelectors:
  - 0 clear
  - 1 players
  - 2 faction{f=Undead}
```

---

[← モブ設定に戻る](Mobs.md) | [← ホームに戻る](../Home.md)
