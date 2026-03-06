# ボスバー (BossBar)

BossBar機能は、エンダードラゴンやウィザーが使用するスタイルと同じように、カスタムモブにHPバーを表示するために使用されますが、カスタマイズのオプションがさらに多いです。

## 構文

```yaml
internal_mobname:
  Type: <mobtype>
  BossBar:
    Enabled: [true/false]
    Title: '[name]'
    Range: [range]
    Color: [color]
    Style: [style]
    CreateFog: [true/false]
    DarkenSky: [true/false]
    PlayMusic: [true/false]
```

### カラー（Color）

利用可能なカラー（大文字小文字を区別）: PINK, BLUE, RED, GREEN, YELLOW, PURPLE, WHITE

### スタイル（Style）

利用可能なスタイル（大文字小文字を区別）: SOLID, SEGMENTED_6, SEGMENTED_10, SEGMENTED_12, SEGMENTED_20

### 範囲（Range）

ボスバーがモブ周辺のプレイヤーに表示される距離。

### 追加オプション

- **CreateFog**: ボスバーの範囲内でプレイヤーの視界に霧のような効果を追加します。
- **DarkenSky**: ウィザーがスポーンしたときに作られる効果と同様に、ボスバーの範囲内で空を暗くします。
- **PlayMusic**: ボスバーの範囲内でボスミュージックを再生します。

## 例

```yaml
SuperCreeper:
  Type: creeper
  Display: '&cスーパークリーパー'
  Health: 20
  BossBar:
    Enabled: true
    Title: 'テスト'
    Range: 20
    Color: RED
    Style: SOLID
```

```yaml
DragonBoss:
  Type: WITHER_SKELETON
  Display: '&5ドラゴンの守護者'
  Health: 1000
  BossBar:
    Enabled: true
    Title: '&5ドラゴンの守護者'
    Range: 50
    Color: PURPLE
    Style: SEGMENTED_20
    CreateFog: true
    DarkenSky: true
    PlayMusic: true
```
