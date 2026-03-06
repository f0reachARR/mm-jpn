# ランダムスポーン (Random Spawns)

ランダムスポーンを使用すると、ワールドでのモブのスポーン方法を完全に制御できます。モブのスポーン場所、頻度、数量を完全にカスタマイズし、モブスポーンを精密にコントロールできます。

## 重要な違い

区別することが重要な主要なランダムスポーンオプションがあります：

### Action: REPLACE

REPLACEアクションは、Minecraftのランダムスポーンシステムによってスポーンされるモブを独自のモブに置き換えるために使用されます。
- Minecraftのスポーンシステムを完全にコントロールできます。
- サーバーでMinecraftのランダムスポナーが無効になっている場合（`gamerule doMobSpawning false`など）、このアクションは何もしません。

### Action: ADD

ADDアクションはMythicMobs独自のスポーンアルゴリズムを利用し、Minecraftのスポーンシステムと同様に、プレイヤーの周りにランダムなスポーンポイントを生成します。
- これらのスポーンポイントは条件なしに生成されるため、任意の光レベルや任意の場所でモブをスポーンできます。
- ADDアクションが機能するには、`plugins/MythicMobs/config/config-spawning.yml`で`GenerateSpawnPoints`を`true`に設定する必要があります。
- サバイバルおよびアドベンチャーモードのプレイヤーの周りのみポイントが生成されます。

### Action: DENY

DENYアクションはモブのスポーンを防ぐために使用できます。
DENYで設定されたランダムスポーンの条件に一致するモブはスポーンしません。

## オプション

### グローバルランダムスポーンオプション

#### 例

```yaml
my_favorite_randomspawn:
  Action: ADD
  Type: cute_zombie
  Level: 2
  Chance: 0.01
  Priority: 10
  UseWorldScaling: false
  Worlds: my_overworld,my_overworld_nether
  Biomes: JUNGLE,PLAINS
  Conditions:
  - day true
```

### 各オプションの説明

- **Action: [action]**
  - 使用するスポーニング方法。デフォルトは"ADD"
  - `Action: ADD` または `Action: REPLACE`

- **Type: [mobtypes]**
  - スポーンするモブのタイプを定義します。複数指定可能
  ```yaml
  Type: SuperZombie
  Type: SkeletalMage,WitchBoss
  ```
  また、重み付きで複数のモブタイプを指定することもできます：
  ```yaml
  Deeps:
    Types:
    - RegularZombie 100
    - BigZombie 50
    - GiantZombie 5
    - HugeZombie 1
  ```

- **Level: [number]**
  - 指定されたモブがスポーンするレベル
  - デフォルトは1

- **Chance: [number]**
  - モブがスポーンする確率
  - デフォルトは1

- **Priority: [number]**
  - 同じスポーンポイントで複数のモブが選ばれた場合に優先するランダムスポーンを決定するために使用される優先度
  - 数値が高いほど選ばれる確率が高い
  - デフォルトは1

- **UseWorldScaling: [true/false]**
  - スポーンするモブのレベルがワールドスケーリング設定の影響を受けるかどうか
  - デフォルトはtrue

- **Conditions: [list]**
  - ランダムスポーンをさらに制限するための条件のリスト
  - 指定された条件のいずれかが満たされない場合、ランダムスポーンは失敗します

- **Worlds: [worldnames]**
  - ランダムスポーンを適用するワールドの名前
  ```yaml
  Worlds: world
  Worlds: world,world_the_end,world_nether
  ```

- **Biomes: [biomes]**
  - 指定されたモブタイプがスポーンできるバイオーム
  ```yaml
  Biomes: SNOWY_TUNDRA,ICE_SPIKES,SNOWY_TAIGA
  ```

- **Reason: [reason]**
  - 一致するMinecraftランダムスポーンの理由
  - [CreatureSpawnEvent.SpawnReason](https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/event/entity/CreatureSpawnEvent.SpawnReason.html)のいずれか

- **PositionType: [LAND/SEA]**
  - このランダムスポーンが陸または海のポイントを使用するかどうか
  - Action: ADDでのみ機能します

- **Cooldown: [number]**
  - 同じランダムスポーンによる2体のモブのスポーン間隔（秒）

- **Structures: [list]**
  - モブがスポーンできる構造物のリスト

#### 構造物スポーンの例

```yaml
Nether_Fortress:
  Types:
  - blaze_wisp 100
  - blazer 60
  Worlds: world_nether
  Chance: 0.02
  Priority: 1
  Action: ADD
  PositionType: LAND
  Structures:
  - 'minecraft:fortress'
```

## 設定ファイルの追加オプション

一般的なランダムスポーンオプションは`MythicMobs/config/config-spawning.yml`ファイルで見つけることができます。
