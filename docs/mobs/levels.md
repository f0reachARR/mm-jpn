# モブレベル (Mob Levels)

モブレベルはモブにレベルを追加するための便利な機能で、いくつかの有用な機能を提供します。

例えば、レベルが上がるにつれてモブのダメージとHPがスケールアップしたり、レベルに応じてより多くのアイテムをドロップしたりすることができます（[ドロップテーブルオプション](../drops/drop-tables.md)の _BonusLevelItems_ を参照）。

より高度な設定では、レベルに応じてドロップを完全に変更したり、レベルに応じて異なるスキルを与えたり、レベルに応じてスポーン場所や方法を変更したりすることができます。

```yaml
Zombie:
  Type: zombie
  Health: 100
  Damage: 10
  Display: '&5ゾンビ レベル - <caster.level>'
  Options:
    MovementSpeed: 0.3
  Drops:
  - myDroptable
  LevelModifiers:
    Health: 5
    Damage: 0.5
```

## LevelModifiers（レベル修飾子）

LevelModifiersセクションに設定されたこれらのオプションは、レベルごとにモブの各統計を指定された数だけ増加させます。これらの統計はベースの統計に追加されます。

```yaml
LevelModifiers:
  Health: [number]
  Damage: [number]
  KnockbackResistance: [number]
  Power: [number]
  Armor: [number]
  MovementSpeed: [number]
```

## ワールドスケーリング (World Scaling)

モブのレベル（ランダムスポーンされるモブ）は、`/MythicMobs/config/config-mobs.yml`にあるワールドスケーリング設定を指定することで、プラグインによって自動的に設定できます。

```yaml
MobLeveling:
  # レベルアップ時のモブ属性のスケーリングに使用
  ScalingEquations:
    Health: V * ((1.05)^(L-1))
    Damage: V * ((1.05)^(L-1))
    Scale: V
  # モブ属性のスケーリングの代替レガシー方法
  DefaultLevelModifiers:
    Health: 0.1
    Armor: 0
    Damage: 0
    KnockbackResistance: 0
    Power: 0
  # ワールドごとのスケーリングオプション
  WorldScaling:
    Default:
      Enabled: true
      ScaleVanillaMobs: true
      PerBlocksFromSpawn: 250
    world2:
      Enabled: true
      PerBlocksFromSpawn: 250
    world2_nether:
      Enabled: false
      PerBlocksFromSpawn: 100
```

上の例では、「world2」を例として、スポーン地点からの距離によってレベルが決まります：

- スポーンから0-249ブロック: レベル0
- スポーンから250-499ブロック: レベル1
- スポーンから500-749ブロック: レベル2
- スポーンから750-999ブロック: レベル3
- スポーンから1000-1249ブロック: レベル4
- 以降同様

これらのオプションは、MythicMobsの[ランダムスポーン](../random-spawns.md)を使用してゲームに召喚されるすべてのモブに自動的に適用されます。

> ワールドスケーリングオプションは、そのワールドの`ScaleVanillaMobs`オプションが`true`に設定されていない限り、バニラオーバーライドには影響しません。
