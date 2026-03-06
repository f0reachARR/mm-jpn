# ステップ3: 最初のモブの作成

基本的な知識、使用方法、どこに使用するかを理解したので、最初のモブを作成します！

ここでは、いくつかの基本的なスキルとアイテムを持つシンプルなモブ「スケルトンキング」を作成します。

## モブファイル

`/plugins/MythicMobs/Mobs/SkeletonKing.yml`

基本的なモブです。内部ID、タイプ、表示名、HP、攻撃力を設定します。

このモブの内部IDは`SkeletonKing`で、これはすべてのモブで一意でなければなりません。`/mm m spawn SkeletonKing`でモブをスポーンするためにこれを使用します。

```yaml
SkeletonKing:
  Type: WITHER_SKELETON
  Display: '&6スケルトンキング'
  Health: 500
  Damage: 10
```

次に、モブにオプションを追加します：

```yaml
SkeletonKing:
  Type: WITHER_SKELETON
  Display: '&6スケルトンキング'
  Health: 500
  Damage: 10
  Options:
    AlwaysShowName: true      # 頭上に名前を常に表示
    MovementSpeed: 0.2         # 移動速度
    MaxCombatDistance: 25      # プレイヤーが戦闘できる最大距離
    PreventOtherDrops: true    # バニラのドロップを停止
```

装備を追加します：

```yaml
SkeletonKing:
  Type: WITHER_SKELETON
  Display: '&6スケルトンキング'
  Health: 500
  Damage: 10
  Options:
    AlwaysShowName: true
    MovementSpeed: 0.2
    MaxCombatDistance: 25
    PreventOtherDrops: true
  Equipment:
  - KingsCrown HEAD
  - IRON_BOOTS FEET
  - SkeletonKingSword HAND
  Drops:
  - SkeletonKingDrops
  Skills:
  - speak{m="我に挑む者はいないのか！";cooldown=20} @PlayersInRadius{r=40} ~onCombat 0.2
  - speak{m="ははははは！死ね、<trigger.name>！"} @PlayersInRadius{r=40} ~onPlayerKill
  - skill{s=SummonSkeletons} @self 0.1
  - skill{s=SmashAttack} @target 0.2
```

## スキルファイル

`/plugins/MythicMobs/Skills/SkeletonKing.yml`

### SummonSkeletons（スケルトン召喚）

```yaml
SummonSkeletons:
  Cooldown: 15
  Skills:
  - message{m="<caster.name><&co> 来い、我が部下よ！"} @PlayersInRadius{r=40}
  - delay 20
  - summon{mob=SKELETON;amount=2;radius=5} @Self
  - delay 20
  - summon{mob=SKELETON;amount=2;radius=5} @Self
  - delay 20
  - summon{mob=SKELETON;amount=2;radius=5} @Self
```

### SmashAttack（スマッシュ攻撃）

```yaml
SmashAttack:
  Cooldown: 8
  Conditions:
  - targetwithin{d=25}
  Skills:
  - message{cooldown=30;m="<mob.name><&co> ははは！愚か者め、砕いてやろう！"} @PlayersInRadius{r=40}
  - teleport @target
  - sound{s=mob.endermen.portal;volume=1.0;pitch=0.5}
  - delay 10
  - damage{amount=5;ignorearmor=true} @PlayersInRadius{r=5}
  - throw{velocity=10;velocityY=5} @PlayersInRadius{r=5}
  - fakeexplosion @Self
```

## アイテムファイル

`/plugins/MythicMobs/Items/SkeletonKing.yml`

```yaml
SkeletonKingSword:
  Id: DIAMOND_SWORD
  Display: '&3スケルトンキングの大剣'
  Lore:
  - '&6スケルトンの王が使用した'
  - '&6強力な剣。'
  Enchantments:
  - DAMAGE_ALL:5
  - KNOCKBACK:2
  - FIRE_ASPECT:2
  Attributes:
    MainHand:
      Health: 10
      MovementSpeed: 0.1

KingsCrown:
  Id: GOLDEN_HELMET
  Display: '&d王の冠'
  Lore:
  - '&6着用者に揺るぎない力を'
  - '&6与える王の冠！'
  Enchantments:
  - PROTECTION_ENVIRONMENTAL:2
  - PROTECTION_PROJECTILE:2
  - PROTECTION_FIRE:2
  - PROTECTION_EXPLOSIONS:2
  Hide:
  - ATTRIBUTES
  - ENCHANTS
  Attributes:
    Head:
      Health: 10
      KnockbackResistance: 10
```

## ドロップテーブルファイル

`/plugins/MythicMobs/DropTables/SkeletonKing.yml`

```yaml
SkeletonKingDrops:
  Drops:
  - SkeletonKingItemDrops 1 1
  - experience 100-150 1
  
SkeletonKingItemDrops:
  Conditions:
  - night
  MinItems: 1
  MaxItems: 2
  Drops:
  - KingsCrown 1 0.01
  - SkeletonKingSword 0.1
  - GOLD_NUGGET 32-64 1
  - DIAMOND 1-12 0.8
```

## テスト

すべてのファイルを作成したら：

1. `/mm reload`でプラグインをリロード
2. `/mm m spawn SkeletonKing`でモブをスポーン
3. モブが正しく動作するか確認！

---

**[<< ステップ2: ファイルとディレクトリ](step2-files.md)** | **[>> ステップ4: 基本的なコマンド](step4-commands.md)**
