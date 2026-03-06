# モブレベル (Mob Levels)

MythicMobs のレベルシステムにより、モブのステータスをレベルに応じてスケーリングできます。

---

## 概要

レベルシステムを使用すると、モブの体力・ダメージ・防御力などをレベルに応じて動的に変化させることができます。これにより、プレイヤーの成長に合わせた敵の難易度調整が可能です。

---

## 基本設定

### モブへのレベル設定

```yaml
MyMob:
  Type: ZOMBIE
  Display: "レベル {level} ゾンビ"
  Health: 20
  Damage: 5
  Level: 1
  Despawn: false
```

表示名で `{level}` プレースホルダーを使うと、現在のレベルを表示できます。

---

## レベルに応じたステータスのスケーリング

### LevelModifiers（レベル修正値）

レベルごとにステータスがどれだけ増加するかを設定します。

```yaml
MyMob:
  Type: ZOMBIE
  Health: 20
  Damage: 5
  LevelModifiers:
    Health: 10         # レベルごとに体力+10
    Damage: 2          # レベルごとにダメージ+2
    Armor: 0.5         # レベルごとに防御力+0.5
    MovementSpeed: 0.01 # レベルごとに移動速度+0.01
    KnockbackResistance: 0.01 # レベルごとにノックバック耐性+0.01
    Power: 1           # レベルごとのパワー修正
```

**例**: レベル5のモブの場合
- 体力: `20 + (5 × 10)` = 70
- ダメージ: `5 + (5 × 2)` = 15

---

## スポーン時のレベル指定

### コマンドでのレベル指定

```
/mm mobs spawn MyMob{level=10}
```

### スポーンポイントでのレベル指定

```yaml
MySpawner:
  MobName: MyMob
  Level: 5              # 固定レベルでスポーン
```

### ランダムレベルでのスポーン

```yaml
MySpawner:
  MobName: MyMob
  Level: 1-10           # 1〜10のランダムレベル
```

---

## ワールドスケーリング

`config.yml` でワールドごとのスケーリング設定が可能です。

```yaml
# config.yml
Mobs:
  LevelSystem:
    Enabled: true
    WorldScaling:
      world: 1.0        # ワールド「world」での倍率
      world_nether: 2.0 # ネザーでは2倍のレベル
      world_the_end: 3.0 # エンドでは3倍のレベル
```

---

## プレイヤーレベルへの追従

プレイヤーの近くにスポーンするモブが、プレイヤーのレベルに合わせてスケーリングするよう設定できます（RPG プラグインとの連携など）。

---

## 表示名でのレベル使用

```yaml
MyMob:
  Display: "&7Lv.&f{level} &cゾンビ"
```

他に使えるプレースホルダー：
- `{level}` : 現在のレベル
- `{health}` : 現在の体力
- `{maxhealth}` : 最大体力
- `{faction}` : 派閥名

---

## 設定例

```yaml
# レベルスケーリングを持つボスモブ
DragonBoss:
  Type: ENDER_DRAGON
  Display: "&5&lLv.{level} 邪悪なドラゴン"
  Health: 500
  Damage: 20
  Level: 1
  LevelModifiers:
    Health: 100
    Damage: 5
    Armor: 1
  BossBar:
    Enabled: true
    Title: "&5Lv.{level} 邪悪なドラゴン"
    Color: PURPLE
  Options:
    Despawn: false
    PreventOtherDrops: true
```

---

[← モブ設定に戻る](Mobs.md) | [← ホームに戻る](../Home.md)
