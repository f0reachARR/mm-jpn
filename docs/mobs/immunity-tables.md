# 免疫テーブル (Immunity Tables)

免疫テーブルを使用すると、各プレイヤーからの無敵ダメージを個別に管理できます。これにより、複数のプレイヤーが同時にモブにダメージを与えることができます。

## 概要

通常のMinecraftでは、エンティティはダメージを受けた後、設定された時間（NoDamageTicks）の間は無敵になります。この無敵はグローバルで、プレイヤーA、B、Cがモブを攻撃している場合でも、一つのプレイヤーの攻撃がモブを無敵にし、他のプレイヤーがその時間にダメージを与えられなくなります。

免疫テーブルはこれを個別に管理します。

## 有効化

```yaml
example_mob:
  Type: zombie
  Modules:
    ImmunityTable: true
```

## 効果

免疫テーブルが有効な場合：
- `NoDamageTicks`は**グローバルではなく、プレイヤーごと**になります
- 複数のプレイヤーが同時に完全なダメージを与えることができます
- マルチプレイのボス戦に最適です

## 例

```yaml
RaidBoss:
  Type: WITHER_SKELETON
  Display: '&cレイドボス'
  Health: 10000
  Modules:
    ThreatTable: true
    ImmunityTable: true
  Options:
    NoDamageTicks: 5  # プレイヤーごとに5ティックの無敵時間
```
