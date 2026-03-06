# スポーナー (Spawners)

スポーナーは、特定の場所に定期的にモブをスポーンさせる機能です。

---

## 概要

スポーナーは `plugins/MythicMobs/Spawners/` フォルダ内のYAMLファイルに定義するか、コマンドで設置します。

---

## スポーナーの設置方法

### コマンドで設置

```
/mm spawners create <スポーナー名> <モブ名>
```

現在立っている位置にスポーナーを設置します。

### YAML ファイルで定義

```yaml
# plugins/MythicMobs/Spawners/MySpawners.yml

MySpawner:
  MobName: SkeletonKing
  World: world
  X: 100
  Y: 64
  Z: 200
  Radius: 5
  MaxMobs: 5
  MobLevel: 10
  Cooldown: 300
  MaxCooldown: 600
  StartDelay: 60
  WarmupTime: 0
  Active: true
  RequirePlayersNearby: true
  CheckForPlayers: 32
  Conditions:
  - isNight
```

---

## スポーナーオプション

| オプション | 型 | デフォルト | 説明 |
|-----------|-----|-----------|------|
| `MobName` | 文字列 | 必須 | スポーンするモブ名 |
| `World` | 文字列 | 必須 | スポーンするワールド名 |
| `X` / `Y` / `Z` | 数値 | 必須 | スポーン座標 |
| `Radius` | 整数 | 0 | スポーン半径（0=固定座標） |
| `MaxMobs` | 整数 | 1 | 同時に存在できる最大モブ数 |
| `MobLevel` | 整数/範囲 | 1 | スポーンするモブのレベル |
| `Cooldown` | 整数 | 300 | スポーン間隔（秒） |
| `MaxCooldown` | 整数 | Cooldown と同じ | 最大クールダウン時間（秒） |
| `StartDelay` | 整数 | 0 | 初回スポーンまでの遅延（秒） |
| `WarmupTime` | 整数 | 0 | ウォームアップ時間（秒） |
| `Active` | 真偽値 | true | スポーナーの有効/無効 |
| `RequirePlayersNearby` | 真偽値 | true | プレイヤーが近くにいる時のみスポーン |
| `CheckForPlayers` | 整数 | 32 | プレイヤー検出範囲（ブロック） |
| `Conditions` | リスト | なし | スポーン条件 |
| `LeashRange` | 整数 | 32 | スポーン地点からモブが離れられる距離 |

---

## コマンド一覧

| コマンド | 説明 |
|---------|------|
| `/mm spawners create <名前> <モブ名>` | スポーナーを作成 |
| `/mm spawners list` | スポーナー一覧を表示 |
| `/mm spawners info <名前>` | スポーナーの詳細を表示 |
| `/mm spawners activate <名前>` | スポーナーを有効化 |
| `/mm spawners deactivate <名前>` | スポーナーを無効化 |
| `/mm spawners remove <名前>` | スポーナーを削除 |
| `/mm spawners pause <名前>` | スポーナーを一時停止 |
| `/mm spawners setmob <名前> <モブ名>` | スポーンするモブを変更 |
| `/mm spawners setcooldown <名前> <秒>` | クールダウンを変更 |
| `/mm spawners setmaxmobs <名前> <数>` | 最大モブ数を変更 |
| `/mm spawners setradius <名前> <半径>` | スポーン半径を変更 |
| `/mm spawners reset <名前>` | スポーナーをリセット |
| `/mm spawners tp <名前>` | スポーナーへテレポート |

---

## スポーン条件

`Conditions` セクションで、スポーンの条件を設定できます：

```yaml
MySpawner:
  MobName: Vampire
  Conditions:
  - isNight            # 夜間のみ
  - isRaining          # 雨の時のみ
```

---

## 設定例

```yaml
# 昼夜で異なるモブをスポーン

DaySpawner:
  MobName: DayGuard
  World: world
  X: 0
  Y: 64
  Z: 0
  Radius: 10
  MaxMobs: 3
  Cooldown: 120
  Conditions:
  - isDay

NightSpawner:
  MobName: NightZombie
  World: world
  X: 0
  Y: 64
  Z: 0
  Radius: 10
  MaxMobs: 5
  Cooldown: 60
  Conditions:
  - isNight

# ボスのスポーナー（1時間に1回スポーン）
BossSpawner:
  MobName: SkeletonKing
  World: world
  X: 500
  Y: 64
  Z: 500
  MaxMobs: 1
  Cooldown: 3600
  MobLevel: 50
  LeashRange: 100
  RequirePlayersNearby: true
  CheckForPlayers: 50
```

---

## 関連ページ

- [ランダムスポーン](Random-Spawns.md)

---

[← ホームに戻る](../Home.md)
