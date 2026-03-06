# ガイド: 最初のランダムスポーン

このガイドでは、モブをワールドにランダムにスポーンさせる方法を説明します。

## 基本的なランダムスポーン

ランダムスポーンは`/plugins/MythicMobs/RandomSpawns/`フォルダにYAMLファイルを作成します。

```yaml
# /plugins/MythicMobs/RandomSpawns/MySpawns.yml

MyFirstRandomSpawn:
  Action: ADD
  Type: CustomZombie
  Worlds: world
  Chance: 0.05
  Priority: 1
```

## 条件付きランダムスポーン

特定の条件下でのみスポーンするモブを設定します：

```yaml
NightZombie:
  Action: ADD
  Type: NightZombieType
  Worlds: world
  Chance: 0.1
  Priority: 5
  Conditions:
  - night true                  # 夜のみ
  - light{l=<7} true            # 光レベルが7以下のみ

ForestSpider:
  Action: ADD
  Type: ForestSpiderType
  Worlds: world
  Biomes: FOREST,BIRCH_FOREST,DARK_FOREST
  Chance: 0.08
  Priority: 3
```

## バニラスポーンの置き換え

ADDアクションの代わりにREPLACEアクションを使用します：

```yaml
ReplaceVanillaZombie:
  Action: REPLACE
  Type: CustomZombie
  Worlds: world
  Chance: 0.5
  Priority: 1
```

## 前提条件の設定

ADDアクションを機能させるには、`/MythicMobs/config/config-spawning.yml`で`GenerateSpawnPoints`を有効にする必要があります：

```yaml
Spawning:
  GenerateSpawnPoints: true
```

## ランダムスポーンのテスト

ランダムスポーンをテストするには：

1. `/mm debugmode true` - デバッグモードを有効にしてランダムスポーンを無効化
2. `/mm mobs spawn MyMobType` - テスト用に手動でスポーン
3. `/mm debugmode false` - デバッグモードを無効化してランダムスポーンを有効化
