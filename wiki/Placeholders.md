# プレースホルダー (Placeholders)

MythicMobs は PlaceholderAPI と連携して、様々な情報をプレースホルダーとして提供します。

---

## 概要

プレースホルダーを使うと、チャット、ボスバー、スコアボードなど様々な場所でMythicMobsの情報を表示できます。

---

## 必要条件

プレースホルダーを使用するには [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/) が必要です。

---

## プレースホルダー一覧

### モブ関連

| プレースホルダー | 説明 |
|----------------|------|
| `%mythicmobs_mob_name%` | ターゲットしているモブの名前 |
| `%mythicmobs_mob_type%` | モブのタイプ |
| `%mythicmobs_mob_health%` | モブの現在体力 |
| `%mythicmobs_mob_maxhealth%` | モブの最大体力 |
| `%mythicmobs_mob_health_percentage%` | モブの体力パーセント |
| `%mythicmobs_mob_level%` | モブのレベル |
| `%mythicmobs_mob_faction%` | モブの派閥 |

### スポーナー関連

| プレースホルダー | 説明 |
|----------------|------|
| `%mythicmobs_spawner_<名前>_count%` | 指定スポーナーのモブ数 |
| `%mythicmobs_spawner_<名前>_maxmobs%` | 指定スポーナーの最大モブ数 |
| `%mythicmobs_spawner_<名前>_cooldown%` | 指定スポーナーのクールダウン |

### サーバー統計

| プレースホルダー | 説明 |
|----------------|------|
| `%mythicmobs_mob_count%` | サーバー全体のMythicMobsモブ数 |
| `%mythicmobs_mob_count_<ワールド>%` | 特定ワールドのモブ数 |

---

## スキル内でのプレースホルダー

スキルの設定内でプレースホルダーを使用できます：

### 組み込みプレースホルダー

| プレースホルダー | 説明 |
|----------------|------|
| `<caster.name>` | スキルを使用したモブの名前 |
| `<caster.health>` | スキルを使用したモブの体力 |
| `<caster.maxhealth>` | スキルを使用したモブの最大体力 |
| `<caster.level>` | スキルを使用したモブのレベル |
| `<target.name>` | ターゲットの名前 |
| `<target.health>` | ターゲットの体力 |
| `<target.maxhealth>` | ターゲットの最大体力 |
| `<target.uuid>` | ターゲットのUUID |
| `<world>` | 現在のワールド名 |
| `<x>` | 現在のX座標 |
| `<y>` | 現在のY座標 |
| `<z>` | 現在のZ座標 |

---

## 使用例

### ボスバーでの使用

```yaml
DragonBoss:
  BossBar:
    Title: "&5Lv.{level} 邪悪なドラゴン &c{health}&7/&c{maxhealth}"
```

### スキルメッセージでの使用

```yaml
Skills:
- message{m="&c<caster.name> が &f<target.name> &cに &4<damage> &cダメージを与えた！"} @PlayersInRadius{r=30} ~onAttack
```

### チャットプラグインとの連携（EssentialsX等）

プレースホルダーAPIと連携すると、チャットフォーマットにMythicMobsの情報を含めることができます。

---

## PlaceholderAPI の設定

MythicMobs の PlaceholderAPI エクスパンションをインストールするには：

```
/papi ecloud download MythicMobs
/papi reload
```

---

## 注意事項

- PlaceholderAPI が必要なプレースホルダーは、PlaceholderAPI がインストールされていないと機能しません。
- スキル内の `<...>` 形式のプレースホルダーはMythicMobs独自のものです。
- `%...%` 形式は PlaceholderAPI のフォーマットです。

---

[← ホームに戻る](Home.md)
