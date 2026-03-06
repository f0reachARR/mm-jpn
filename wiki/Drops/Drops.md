# ドロップ設定 (Drops)

MythicMobs では、モブが死亡した際のドロップを細かく設定できます。

---

## 概要

ドロップは `Drops` フィールドでモブに直接指定するか、`plugins/MythicMobs/Drops/` フォルダのドロップテーブルを使用します。

---

## インラインドロップ（モブ定義内に直接書く）

```yaml
MobName:
  Drops:
  - <アイテム> <数量> <確率>
  - <ドロップタイプ> <オプション>
```

---

## ドロップの種類

### バニラアイテムのドロップ

```yaml
Drops:
- DIAMOND 1-3 0.5         # ダイヤモンドを1〜3個、50%の確率でドロップ
- EMERALD 1 0.1           # エメラルドを1個、10%の確率でドロップ
- BONE 2-5 1.0            # 骨を2〜5個、必ずドロップ
- EXPERIENCE 100-200      # 経験値を100〜200ドロップ
```

### カスタムアイテムのドロップ

```yaml
Drops:
- MyCustomSword 1 0.05     # カスタムアイテム「MyCustomSword」を5%の確率でドロップ
- LegendaryArmor 1 0.01    # 1%の確率でドロップ
```

### ドロップテーブルの参照

```yaml
Drops:
- drops:MyDropTable 1 1.0  # ドロップテーブルを参照
```

### 経験値

```yaml
Drops:
- EXPERIENCE 50-100        # 50〜100の経験値をドロップ
```

---

## ドロップのフォーマット

### 基本形式

```
<アイテム名> [最小数]-[最大数] [確率]
```

| パラメータ | 説明 | デフォルト |
|-----------|------|-----------|
| アイテム名 | Minecraft のマテリアル名またはカスタムアイテム名 | 必須 |
| 数量 | ドロップ数（固定値または `最小-最大` 形式） | 1 |
| 確率 | ドロップ確率（0.0〜1.0） | 1.0 |

---

## 設定例

```yaml
SkeletonKing:
  Type: SKELETON
  Display: "&cスケルトンキング"
  Health: 500
  Options:
    PreventOtherDrops: true     # バニラドロップを防止
  Drops:
  - BONE 5-15 1.0               # 骨を5〜15個（確実）
  - ARROW 10-30 1.0             # 矢を10〜30個（確実）
  - EMERALD 1-5 0.8             # エメラルドを1〜5個（80%）
  - DIAMOND 1-3 0.3             # ダイヤモンドを1〜3個（30%）
  - SkeletonKingHelmet 1 0.05   # 専用ヘルメットを（5%）
  - drops:SkeletonKingTable     # ドロップテーブルを参照
  - EXPERIENCE 200-500          # 経験値200〜500
```

---

## バニラドロップの制御

### PreventOtherDrops

`true` にすると、バニラのデフォルトドロップ（骨、矢など）が無効になります。

```yaml
Options:
  PreventOtherDrops: true
```

### PreventMobKillDrops

他のモブによって倒された場合のドロップを防止します。

```yaml
Options:
  PreventMobKillDrops: true
```

---

## 関連ページ

- [ドロップテーブル](Drop-Tables.md)
- [カスタムアイテム](../Items/Items.md)

---

[← ホームに戻る](../Home.md)
