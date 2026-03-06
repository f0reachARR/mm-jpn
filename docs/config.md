# 設定ファイル (Config)

MythicMobsには複数の設定ファイルがあります。

## 設定ファイルの場所

設定ファイルは`/plugins/MythicMobs/config/`フォルダにあります：

- `config.yml` - 主要な設定ファイル
- `config-mobs.yml` - モブ関連の設定
- `config-spawning.yml` - スポーン関連の設定

## config.yml

主要な設定ファイルは以下のようなセクションを含みます：

```yaml
MythicMobs:
  # プラグインの基本設定
  Language: en
  DebugLevel: 0
  
  # セーブ設定
  SaveInterval: 600  # 秒単位
  
  # モブHP表示設定
  Mobs:
    ShowHealth:
      Enabled: false
      Radius: 30
      Formatting: "&cHP: <hp>/<maxhp>"
```

## config-mobs.yml

モブ関連の設定：

```yaml
MobLeveling:
  # モブ属性のスケーリング方程式
  ScalingEquations:
    Health: V * ((1.05)^(L-1))
    Damage: V * ((1.05)^(L-1))
    Scale: V
  
  # ワールドごとのスケーリングオプション
  WorldScaling:
    Default:
      Enabled: true
      ScaleVanillaMobs: false
      PerBlocksFromSpawn: 250
```

## config-spawning.yml

スポーン関連の設定：

```yaml
Spawning:
  # スポーンポイントの生成
  GenerateSpawnPoints: false  # ADDスポーンを使用する場合はtrueに設定
  
  # スポーンポイント生成の設定
  SpawnPointSettings:
    MinimumDistanceFromPlayer: 24
    MaximumDistanceFromPlayer: 48
    
  # バニラスポーンの制御
  PreventOtherDrops: false
```

## 詳細設定

MythicMobsの設定ファイルは多くのオプションを提供しています。最新の完全な設定ファイルの内容は[公式Wiki](https://git.lumine.io/mythiccraft/MythicMobs/-/wikis/Config/config-spawning)で確認できます。
