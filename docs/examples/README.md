# サンプル (Examples)

よく使用されるMythicMobsの設定サンプルです。

## モブのサンプル

### 基本的なカスタムゾンビ

```yaml
CustomZombie:
  Type: ZOMBIE
  Display: '&2カスタムゾンビ'
  Health: 50
  Damage: 5
  Options:
    PreventOtherDrops: true
    MovementSpeed: 0.25
  Drops:
  - exp 10 1
  - rotten_flesh 1-3 0.8
```

### ボスモブ

```yaml
CaveTroll:
  Type: IRON_GOLEM
  Display: '&4洞窟のトロール'
  Health: 1000
  Damage: 20
  Options:
    AlwaysShowName: true
    PreventOtherDrops: true
    MovementSpeed: 0.18
    KnockbackResistance: 0.8
  BossBar:
    Enabled: true
    Title: '洞窟のトロール'
    Color: RED
    Style: SEGMENTED_20
    Range: 40
  Equipment:
  - iron_sword HAND
  Drops:
  - TrollDropTable
  Skills:
  - skill{s=Smash} @target ~onAttack 0.3
  - skill{s=RoarSkill} ~onSpawn
  - speak{m="&4うおぉぉぉ！！！";distance=50} @players ~onDeath
```

### NPCモブ

```yaml
TownGuard:
  Type: ZOMBIE
  Display: '&7衛兵'
  Health: 100
  Damage: 8
  Options:
    AlwaysShowName: true
    Despawn: PERSISTENT
    NoAI: false
    PreventOtherDrops: true
  Disguise: player Steve
  Equipment:
  - IRON_HELMET HEAD
  - IRON_CHESTPLATE CHEST
  - IRON_LEGGINGS LEGS
  - IRON_BOOTS FEET
  - IRON_SWORD HAND
  AIGoalSelectors:
  - clear
  - lookatplayers
  - randomlookaround
  AITargetSelectors:
  - clear
```

## スキルのサンプル

### 火球の一斉射

```yaml
FireballVolley:
  Cooldown: 5
  Skills:
  - fireball{yield=2} @target
  - delay 5
  - fireball{yield=2} @target
  - delay 5
  - fireball{yield=2} @target
```

### 周囲への攻撃

```yaml
AoESmash:
  Skills:
  - effect:particles{p=explosion_large;amount=5} @self
  - sound{s=entity.iron_golem.attack}
  - damage{amount=10;ignorearmor=false} @PlayersInRadius{r=5}
  - throw{velocity=5;velocityY=3} @PlayersInRadius{r=5}
  - message{m="&c粉砕！！"} @PlayersInRadius{r=20}
```

### テレポート

```yaml
BossCharge:
  Cooldown: 10
  Conditions:
  - targetwithin{d=20}
  Skills:
  - message{m="&c逃がさぬ！"} @PlayersInRadius{r=30}
  - teleport @target
  - sound{s=entity.enderman.teleport}
  - effect:particles{p=portal;amount=20} @self
  - damage{amount=8} @PlayersInRadius{r=3}
```

## アイテムのサンプル

### カスタム武器

```yaml
DragonSword:
  Id: NETHERITE_SWORD
  Display: '&5ドラゴンの剣'
  Lore:
  - '&7古代のドラゴンが使用した剣'
  - '&7炎の力が宿っている'
  Enchantments:
  - DAMAGE_ALL:5
  - FIRE_ASPECT:2
  - DURABILITY:3
  Attributes:
    MainHand:
      Health: 4
```

### 防具セット

```yaml
GuardArmor:
  Id: IRON_CHESTPLATE
  Display: '&7衛兵の甲冑'
  Lore:
  - '&7衛兵が使用する頑丈な甲冑'
  Enchantments:
  - PROTECTION_ENVIRONMENTAL:3
  - DURABILITY:2
  Hide:
  - ENCHANTS
```

## ドロップテーブルのサンプル

```yaml
BossDropTable:
  Conditions:
  - playerwithin{d=50}
  MinItems: 2
  MaxItems: 4
  Drops:
  - exp 500-1000 1
  - DragonSword 1 0.05      # 5%の確率でドラゴンの剣
  - diamond 1-5 0.5         # 50%の確率でダイヤモンド
  - emerald 5-10 0.8        # 80%の確率でエメラルド
  - GOLD_NUGGET 10-20 1     # 確実にゴールドナゲット
```

## ランダムスポーンのサンプル

```yaml
# 砂漠バイオームにゾンビハンターをスポーン
DesertZombieHunter:
  Action: ADD
  Type: CustomZombie
  Worlds: world
  Biomes: DESERT,DESERT_HILLS
  Chance: 0.02
  Priority: 5
  Conditions:
  - night true
```
