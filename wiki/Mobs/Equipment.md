# 装備 (Equipment)

MythicMobs のモブにカスタム装備を持たせることができます。

---

## 基本構文

```yaml
MobName:
  Equipment:
  - <アイテム> <スロット>
  - <アイテム>:<ドロップ確率> <スロット>
```

---

## 装備スロット一覧

| スロット | 説明 |
|---------|------|
| `HAND` | メインハンド（右手） |
| `OFF_HAND` | オフハンド（左手） |
| `HEAD` | 頭 |
| `CHEST` | 胸 |
| `LEGS` | 脚 |
| `FEET` | 足 |

---

## バニラアイテムの装備

```yaml
Equipment:
- DIAMOND_SWORD HAND
- SHIELD OFF_HAND
- DIAMOND_HELMET HEAD
- DIAMOND_CHESTPLATE CHEST
- DIAMOND_LEGGINGS LEGS
- DIAMOND_BOOTS FEET
```

---

## カスタムアイテムの装備

MythicMobs で定義したカスタムアイテムを使用できます：

```yaml
Equipment:
- MyLegendarySword HAND
- AncientShield OFF_HAND
```

---

## ドロップ確率の設定

アイテム名の後に `:確率` を付けると、そのアイテムをドロップする確率を設定できます。

```yaml
Equipment:
- DIAMOND_SWORD:0.0 HAND       # ドロップしない（0%）
- IRON_HELMET:0.5 HEAD         # 50% の確率でドロップ
- LEATHER_BOOTS:1.0 FEET       # 必ずドロップ（100%）
```

---

## エンチャントの付与

バニラエンチャントをアイテムに付与できます：

```yaml
Equipment:
- DIAMOND_SWORD{enchantments=[DAMAGE_ALL:5,FIRE_ASPECT:2]} HAND
```

---

## 注意事項

- ドロップ確率はモブ設定の `PreventOtherDrops` の影響を受けます。
- `PreventItemPickup: true` を設定すると、モブが地面のアイテムを拾わなくなります。
- 一部のエンティティタイプは特定のスロットに対応していない場合があります。

---

## 設定例

```yaml
EliteKnight:
  Type: ZOMBIE
  Display: "&6エリート騎士"
  Health: 200
  Equipment:
  - DIAMOND_SWORD:0.05 HAND        # 5% でダイヤモンドソードをドロップ
  - SHIELD:0.1 OFF_HAND            # 10% でシールドをドロップ
  - DIAMOND_HELMET:0.1 HEAD        # 10% でダイヤモンドヘルメットをドロップ
  - DIAMOND_CHESTPLATE:0.05 CHEST  # 5% でダイヤモンドチェストプレートをドロップ
  - DIAMOND_LEGGINGS:0.05 LEGS     # 5% でダイヤモンドレギンスをドロップ
  - DIAMOND_BOOTS:0.05 FEET        # 5% でダイヤモンドブーツをドロップ
  Options:
    PreventOtherDrops: true         # バニラドロップは防止
```

---

[← モブ設定に戻る](Mobs.md) | [← ホームに戻る](../Home.md)
