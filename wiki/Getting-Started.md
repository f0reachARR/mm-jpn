# はじめに (Getting Started)

MythicMobs へようこそ！このページでは、プラグインのインストールから最初のカスタムモブの作成まで、基本的な手順を説明します。

---

## インストール

### 必要条件

- **Minecraft バージョン**: 1.16 以降推奨（最新バージョン推奨）
- **サーバーソフト**: Spigot / Paper / その他 Bukkit 互換サーバー
- **Java**: Java 11 以降

### インストール手順

1. [MythicMobs の配布ページ](https://www.spigotmc.org/resources/mythicmobs.5702/)から最新版の `.jar` ファイルをダウンロードします。
2. ダウンロードした `.jar` ファイルをサーバーの `plugins/` フォルダに配置します。
3. サーバーを起動（または再起動）します。
4. `plugins/MythicMobs/` フォルダが自動的に生成されます。

---

## 設定ファイル

MythicMobs を初めて起動すると、`plugins/MythicMobs/` フォルダ内に以下のような構造でファイルが生成されます：

```
plugins/MythicMobs/
├── config.yml          # メイン設定ファイル
├── Mobs/               # カスタムモブの定義フォルダ
│   └── ExampleMobs.yml
├── Skills/             # カスタムスキルの定義フォルダ
│   └── ExampleSkills.yml
├── Items/              # カスタムアイテムの定義フォルダ
│   └── ExampleItems.yml
├── Drops/              # ドロップテーブルの定義フォルダ
│   └── ExampleDrops.yml
└── Spawners/           # スポーナーの定義フォルダ
    └── ExampleSpawners.yml
```

### config.yml の主な設定

```yaml
# config.yml
Options:
  Debug: false             # デバッグモードの有効化
  Language: ja             # 言語設定
  UseMetrics: true         # 統計情報の送信
  
Mobs:
  MaxMobsPerChunk: -1      # チャンクあたりの最大モブ数（-1 = 無制限）
  
Spawning:
  PreventOtherDrops: false # バニラドロップの防止
```

---

## 最初のカスタムモブを作る

`plugins/MythicMobs/Mobs/` フォルダ内の任意の `.yml` ファイルにモブを定義できます。

### シンプルなモブの例

```yaml
# plugins/MythicMobs/Mobs/MyMobs.yml

SkeletonKing:
  Type: SKELETON
  Display: "&cスケルトンキング"
  Health: 100
  Damage: 10
  Equipment:
  - IRON_SWORD HAND
  - IRON_HELMET HEAD
  Options:
    MovementSpeed: 0.3
    KnockbackResistance: 0.5
  Skills:
  - skill{s=FireballSkill} ~onTimer:100
```

### モブをスポーンさせる

コマンドを使ってモブをスポーンさせます：

```
/mm mobs spawn SkeletonKing
```

ターゲット座標を指定する場合：

```
/mm mobs spawn SkeletonKing 1 ~ 100 50 100
```

---

## よく使うコマンド

| コマンド | 説明 |
|---------|------|
| `/mm mobs spawn <MobName>` | 指定したモブをスポーン |
| `/mm mobs spawn <MobName> <数> <ワールド> <X> <Y> <Z>` | 座標を指定してスポーン |
| `/mm mobs kill all` | 全てのカスタムモブを削除 |
| `/mm mobs list` | スポーン中のモブ一覧を表示 |
| `/mm reload` | 設定をリロード |
| `/mm items get <ItemName>` | カスタムアイテムを取得 |
| `/mm test cast <SkillName>` | スキルをテスト実行 |
| `/mm debug <level>` | デバッグレベルを設定（0〜5）|

---

## 権限 (Permissions)

| 権限ノード | 説明 |
|-----------|------|
| `mythicmobs.admin` | 全ての管理コマンドへのアクセス |
| `mythicmobs.command.spawn` | モブのスポーンコマンド |
| `mythicmobs.command.reload` | リロードコマンド |
| `mythicmobs.command.info` | 情報表示コマンド |

---

## 次のステップ

- [モブの詳細設定](Mobs/Mobs.md)を学ぶ
- [スキルの作り方](Skills/Skills.md)を学ぶ
- [カスタムアイテム](Items/Items.md)を作成する

---

[← ホームに戻る](Home.md)
