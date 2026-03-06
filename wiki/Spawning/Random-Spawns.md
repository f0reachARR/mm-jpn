# ランダムスポーン (Random Spawns)

ランダムスポーン機能を使うと、ワールド内でモブをランダムにスポーンさせることができます。

---

## 概要

ランダムスポーンは `plugins/MythicMobs/` の `config.yml` または専用の設定ファイルで定義します。バニラのモブスポーンの代わりに、またはそれに加えてカスタムモブをワールドにスポーンさせます。

---

## 基本設定（config.yml）

```yaml
# config.yml

Spawning:
  WorldSettings:
    world:                    # ワールド名
      EnableRandomSpawning: true
      RandomSpawning:
        Rate: 10              # スポーン頻度（ゲームデフォルト比較）
        SpawnOnSurface: true  # 地表スポーンを有効化
        SpawnUnderground: true # 地下スポーンを有効化
        SpawnInLiquids: false  # 液体中スポーンを有効化
```

---

## ランダムスポーン設定ファイル

`plugins/MythicMobs/RandomSpawns/` フォルダに設定ファイルを作成します：

```yaml
# RandomSpawns/OverworldSpawns.yml

MyRandomSpawn:
  MobName: SkeletonWarrior
  World: world
  UseWorldSettings: true
  Level: 1-10
  Cooldown: 300
  Chance: 0.1               # スポーンチャンス（0.0〜1.0）
  MaxMobs: 50               # ワールド内の最大数
  Priority: 5               # 優先度（高いほど優先）
  PositionType: GROUND      # スポーン位置タイプ
  Biomes:                   # スポーンするバイオーム（省略で全バイオーム）
  - FOREST
  - PLAINS
  Conditions:
  - isNight
```

---

## スポーン位置タイプ

| タイプ | 説明 |
|--------|------|
| `GROUND` | 地表 |
| `UNDERGROUND` | 地下 |
| `SEA` | 海中 |
| `AIR` | 空中 |
| `ANY` | どこでも |

---

## バイオーム一覧（主要なもの）

| バイオーム名 | 説明 |
|------------|------|
| `PLAINS` | 平原 |
| `FOREST` | 森 |
| `TAIGA` | タイガ |
| `DESERT` | 砂漠 |
| `JUNGLE` | ジャングル |
| `SWAMP` | 沼地 |
| `OCEAN` | 海洋 |
| `DEEP_OCEAN` | 深海 |
| `MOUNTAINS` | 山岳 |
| `NETHER_WASTES` | ネザー荒野 |
| `SOUL_SAND_VALLEY` | ソウルサンドの谷 |
| `CRIMSON_FOREST` | クリムゾンの森 |
| `WARPED_FOREST` | 歪んだ森 |
| `BASALT_DELTAS` | 玄武岩のデルタ |
| `THE_END` | エンド |

---

## 完全な設定例

```yaml
# ランダムスポーン設定例

# 夜に出現する強いゾンビ
NightZombieSpawn:
  MobName: EliteZombie
  World: world
  Level: 5-15
  Chance: 0.2
  MaxMobs: 30
  PositionType: GROUND
  Biomes:
  - PLAINS
  - FOREST
  - TAIGA
  Conditions:
  - isNight

# ネザー専用のブレイズ
NetherBlazeSpawn:
  MobName: EnhancedBlaze
  World: world_nether
  Level: 10-25
  Chance: 0.15
  MaxMobs: 20
  PositionType: UNDERGROUND
  Biomes:
  - NETHER_WASTES
  - CRIMSON_FOREST

# 砂漠の昼間に出現するゾンビ
DesertZombieSpawn:
  MobName: DesertMummy
  World: world
  Level: 1-8
  Chance: 0.1
  MaxMobs: 15
  PositionType: GROUND
  Biomes:
  - DESERT
  Conditions:
  - isDay

# 洞窟内のモンスター
CaveMonsterSpawn:
  MobName: CaveSpider
  World: world
  Level: 3-12
  Chance: 0.3
  MaxMobs: 40
  PositionType: UNDERGROUND
```

---

## 注意事項

- ランダムスポーンはサーバーの TPS（Ticks Per Second）に影響する場合があります。
- `MaxMobs` の設定でワールド内のモブ数を適切に制限してください。
- `Chance` の値が高すぎると、ワールドが過密状態になる可能性があります。
- バイオームフィルタリングを使うと、スポーンをより細かく制御できます。

---

[← スポーナーに戻る](Spawners.md) | [← ホームに戻る](../Home.md)
