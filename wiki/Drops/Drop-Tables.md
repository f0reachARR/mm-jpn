# ドロップテーブル (Drop Tables)

ドロップテーブルは、複数のモブで共有できる再利用可能なドロップセットです。

---

## 概要

ドロップテーブルは `plugins/MythicMobs/Drops/` フォルダ内のYAMLファイルに定義します。複数のモブから参照でき、ドロップ設定を一元管理できます。

---

## 基本構文

```yaml
# plugins/MythicMobs/Drops/MyDropTables.yml

MyDropTable:
  Drops:
  - <アイテム> <数量> <確率>
  - <アイテム> <数量> <確率>
  MinItems: 1              # 最低ドロップ数
  MaxItems: 5              # 最大ドロップ数
  Conditions:
  - <条件>
```

---

## モブからの参照

```yaml
# Mobs/MyMob.yml

SkeletonKing:
  Drops:
  - drops:SkeletonKingTable     # ドロップテーブル名で参照
```

---

## ドロップテーブルの種類

### 通常のドロップテーブル

```yaml
CommonDropTable:
  Drops:
  - STONE 1-3 0.5
  - COBBLESTONE 2-5 0.3
  - COAL 1-2 0.2
```

### 条件付きドロップ

`Conditions` セクションで、ドロップ条件を設定できます：

```yaml
NightDropTable:
  Conditions:
  - isNight
  Drops:
  - BONE 2-5 1.0
  - ROTTEN_FLESH 1-3 0.5
```

### ドロップ数の制限

```yaml
LootTable:
  MinItems: 1      # 最低でも1つドロップ
  MaxItems: 3      # 最大3つドロップ
  Drops:
  - DIAMOND 1 0.1
  - EMERALD 1 0.2
  - GOLD_INGOT 1-3 0.4
  - IRON_INGOT 2-5 0.6
```

### ネストされたドロップテーブル

ドロップテーブルから別のドロップテーブルを参照できます：

```yaml
BossDropTable:
  Drops:
  - drops:CommonDropTable       # 別のドロップテーブルを参照
  - drops:RareDropTable 1 0.1   # 10%の確率で別テーブルを参照
  - DIAMOND 1-3 0.5
```

---

## 完全な設定例

```yaml
# plugins/MythicMobs/Drops/BossDrops.yml

# スケルトンキングのドロップテーブル
SkeletonKingTable:
  Drops:
  # 通常ドロップ
  - BONE 10-20 1.0
  - ARROW 10-20 1.0
  # レアドロップ
  - DIAMOND 1-5 0.3
  - EMERALD 1-3 0.5
  # 超レアドロップ
  - drops:SkeletonKingRareTable 1 0.1   # 10%の確率で超レアテーブル
  # 経験値
  - EXPERIENCE 200-500

# スケルトンキングの超レアドロップ（10%の確率で抽選）
SkeletonKingRareTable:
  MinItems: 1
  MaxItems: 1
  Drops:
  - SkeletonKingCrown 1 0.4     # 専用クラウン（40%）
  - SkeletonKingSword 1 0.4     # 専用ソード（40%）
  - SkeletonKingStaff 1 0.2     # 専用スタッフ（20%）

# 全モブ共通の基本ドロップテーブル
CommonLoot:
  Drops:
  - BONE 1-3 0.5
  - ROTTEN_FLESH 1-2 0.4
  - ARROW 1-5 0.3

# ハードモード（昼間）専用ドロップ
HardmodeDayDrop:
  Conditions:
  - isDay
  Drops:
  - SUNSTONE 1 0.05             # カスタムアイテム
  - DIAMOND 1-2 0.2
```

---

## ドロップテーブルの活用

複数のモブで同じドロップテーブルを共有：

```yaml
# Mobs/UndeadMobs.yml

Zombie01:
  Drops:
  - drops:CommonLoot
  - ROTTEN_FLESH 2-4 1.0

Skeleton01:
  Drops:
  - drops:CommonLoot
  - BONE 2-4 1.0
  - ARROW 5-10 1.0

SkeletonKing:
  Drops:
  - drops:SkeletonKingTable
  Options:
    PreventOtherDrops: true
```

---

## 注意事項

- ドロップテーブルの確率は各アイテムが独立して判定されます（一つ選ばれるのではなく、それぞれが確率で判定）。
- `MinItems` / `MaxItems` を使うと、ドロップされる最大アイテム数を制限できます。
- ドロップテーブル名はユニークである必要があります（同じ名前のテーブルが複数あると意図しない動作になる場合があります）。

---

[← ドロップ設定に戻る](Drops.md) | [← ホームに戻る](../Home.md)
