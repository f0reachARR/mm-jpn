# ボスバー (BossBar)

MythicMobs のボスバー機能を使うと、モブの体力バーをゲーム画面上部に表示できます。

---

## 基本構文

```yaml
MobName:
  BossBar:
    Enabled: true
    Title: "<ボスバーのタイトル>"
    Range: 60
    Color: RED
    Style: SOLID
    CreateFog: false
    DarkenSky: false
    PlayBossMusic: false
```

---

## オプション一覧

| オプション | 型 | デフォルト | 説明 |
|-----------|-----|-----------|------|
| `Enabled` | 真偽値 | false | ボスバーを表示するか |
| `Title` | 文字列 | モブ名 | ボスバーに表示するタイトル |
| `Range` | 整数 | 60 | プレイヤーに表示される範囲（ブロック） |
| `Color` | 文字列 | PURPLE | ボスバーの色 |
| `Style` | 文字列 | SOLID | ボスバーのスタイル |
| `CreateFog` | 真偽値 | false | フォグエフェクトを作成 |
| `DarkenSky` | 真偽値 | false | 空を暗くする |
| `PlayBossMusic` | 真偽値 | false | ボスBGMを再生（エンダードラゴン音楽） |

---

## ボスバーの色

| 色 | 表示 |
|----|------|
| `PINK` | ピンク |
| `BLUE` | 青 |
| `RED` | 赤 |
| `GREEN` | 緑 |
| `YELLOW` | 黄色 |
| `PURPLE` | 紫 |
| `WHITE` | 白 |

---

## ボスバーのスタイル

| スタイル | 表示 |
|---------|------|
| `SOLID` | 分割なし（連続バー） |
| `SEGMENTED_6` | 6分割 |
| `SEGMENTED_10` | 10分割 |
| `SEGMENTED_12` | 12分割 |
| `SEGMENTED_20` | 20分割 |

---

## タイトルのプレースホルダー

| プレースホルダー | 説明 |
|----------------|------|
| `{level}` | モブのレベル |
| `{health}` | 現在の体力 |
| `{maxhealth}` | 最大体力 |
| `{name}` | モブの名前 |
| `{faction}` | 派閥名 |

---

## 設定例

```yaml
DragonBoss:
  Type: ENDER_DRAGON
  Display: "&5&l邪悪なドラゴン"
  Health: 1000
  BossBar:
    Enabled: true
    Title: "&5&l邪悪なドラゴン &7[&c{health}&7/&c{maxhealth}&7]"
    Range: 80
    Color: PURPLE
    Style: SEGMENTED_10
    DarkenSky: true
    PlayBossMusic: true
    CreateFog: false
```

---

## 注意事項

- ボスバーはプレイヤーが指定した `Range` 内にいる場合のみ表示されます。
- `DarkenSky: true` はエンダードラゴンのような演出に使用できます。
- `PlayBossMusic: true` はエンダードラゴン戦のBGMを再生します。
- 複数のボスが近くにいる場合、複数のボスバーが表示されます。

---

[← モブ設定に戻る](Mobs.md) | [← ホームに戻る](../Home.md)
