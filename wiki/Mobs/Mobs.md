# モブの設定 (Mobs)

MythicMobs では、YAML ファイルを使って詳細なカスタムモブを作成できます。

---

## 基本構造

```yaml
MobName:
  Type: <EntityType>
  Display: "<表示名>"
  Health: <体力>
  Damage: <ダメージ>
  Armor: <防御力>
  BossBar:
    Enabled: true
    Title: "<ボスバータイトル>"
  Faction: "<派閥名>"
  Level: <レベル>
  Options:
    <オプション>
  Disguise:
    <変装設定>
  Skills:
  - <スキル定義>
  AIGoalSelectors:
  - <AIゴール>
  AITargetSelectors:
  - <AIターゲット>
  Drops:
  - <ドロップ定義>
  Equipment:
  - <装備定義>
  KillMessages:
  - "<キルメッセージ>"
```

---

## 主要フィールド一覧

### Type（エンティティタイプ）

モブのベースとなる Minecraft エンティティを指定します。

```yaml
Type: ZOMBIE
```

使用可能なエンティティタイプの例：

| タイプ | 説明 |
|--------|------|
| `ZOMBIE` | ゾンビ |
| `SKELETON` | スケルトン |
| `CREEPER` | クリーパー |
| `SPIDER` | スパイダー |
| `ENDERMAN` | エンダーマン |
| `WITCH` | ウィッチ |
| `BLAZE` | ブレイズ |
| `ENDER_DRAGON` | エンダードラゴン |
| `WITHER` | ウィザー |
| `PLAYER` | プレイヤー（外見のみ） |

Minecraft のすべてのエンティティタイプが使用可能です。

### Display（表示名）

ゲーム内でモブの頭上に表示される名前です。カラーコード (`&`) と MiniMessage 形式をサポートします。

```yaml
Display: "&c&lスケルトンキング"
Display: "<red><bold>スケルトンキング</bold></red>"
```

### Health（体力）

モブの最大体力を設定します（デフォルト: エンティティの基本体力）。

```yaml
Health: 200
```

### Damage（ダメージ）

モブの基本攻撃ダメージを設定します。

```yaml
Damage: 10
```

### Armor（防御力）

モブの防御力を設定します。

```yaml
Armor: 5
```

### Faction（派閥）

モブの派閥を設定します。同じ派閥のモブは互いに敵対しません。

```yaml
Faction: "UndeadArmy"
```

### Level（レベル）

モブの固定レベルを設定します（レベルシステム使用時）。

```yaml
Level: 10
```

---

## Skills（スキル）

モブが使用するスキルを定義します。

```yaml
Skills:
- skill{s=FireballSkill} ~onTimer:100 0.5
- mechanic{...} ~onDeath
- effect:particles{...} ~onDamaged 0.3
```

形式：`<スキル定義> [トリガー] [クールダウン] [確率]`

詳細は [スキルの設定](../Skills/Skills.md) を参照してください。

---

## Equipment（装備）

モブが装備するアイテムを定義します。

```yaml
Equipment:
- DIAMOND_SWORD HAND         # メインハンド
- SHIELD OFF_HAND            # オフハンド
- DIAMOND_HELMET HEAD        # 頭
- DIAMOND_CHESTPLATE CHEST   # 胸
- DIAMOND_LEGGINGS LEGS      # 脚
- DIAMOND_BOOTS FEET         # 足
```

カスタムアイテムも使用可能です：

```yaml
Equipment:
- MyCustomSword HAND
```

ドロップ確率の指定：

```yaml
Equipment:
- DIAMOND_SWORD:0.5 HAND     # 50% の確率でドロップ
```

---

## Drops（ドロップ）

モブが死亡時にドロップするアイテムを定義します。

```yaml
Drops:
- DIAMOND 1-3 0.5            # ダイヤモンドを1〜3個、50%の確率でドロップ
- EMERALD 1 0.1              # エメラルドを1個、10%の確率でドロップ
- MyCustomItem 1 0.05        # カスタムアイテムを1個、5%の確率でドロップ
- drops:MyDropTable          # ドロップテーブルを参照
```

詳細は [ドロップの設定](../Drops/Drops.md) を参照してください。

---

## AIGoalSelectors（AIゴール）

モブの行動AIを設定します。数字は優先度（低いほど高優先）です。

```yaml
AIGoalSelectors:
- 0 clear                    # デフォルトAIをクリア
- 1 meleeattack              # 近接攻撃
- 2 randomstroll             # ランダム歩行
- 3 look                     # プレイヤーを見る
```

主なAIゴール：

| ゴール | 説明 |
|--------|------|
| `meleeattack` | 近接攻撃 |
| `rangedattack` | 遠距離攻撃 |
| `randomstroll` | ランダム歩き回り |
| `randomlook` | ランダム方向を見る |
| `look` | ターゲットを見る |
| `flee` | ターゲットから逃げる |
| `float` | 水に浮く |
| `opendoor` | ドアを開ける |
| `avoidplayers` | プレイヤーを避ける |

## AITargetSelectors（AIターゲット）

モブが攻撃するターゲットを設定します。

```yaml
AITargetSelectors:
- 0 clear
- 1 players
- 2 notself
```

主なAIターゲット：

| ターゲット | 説明 |
|-----------|------|
| `players` | プレイヤーをターゲット |
| `monsters` | モンスターをターゲット |
| `notself` | 自分以外をターゲット |
| `target` | 既存のターゲットを維持 |

---

## KillMessages（キルメッセージ）

プレイヤーがこのモブに倒された際のメッセージです。

```yaml
KillMessages:
- "&cあなたはスケルトンキングに倒されました！"
- "&4{player} はスケルトンキングの手にかかった..."
```

プレースホルダー：
- `{player}` : プレイヤー名
- `{mob}` : モブの表示名

---

## 完全な設定例

```yaml
SkeletonKing:
  Type: SKELETON
  Display: "&c&lスケルトンキング"
  Health: 500
  Damage: 15
  Armor: 10
  Faction: Undead
  BossBar:
    Enabled: true
    Title: "&c&lスケルトンキング"
    Range: 60
    Color: RED
    Style: SOLID
  Options:
    MovementSpeed: 0.25
    KnockbackResistance: 0.8
    PreventOtherDrops: true
    PreventItemPickup: true
    Despawn: false
  Equipment:
  - BONE_SWORD HAND
  - IRON_HELMET HEAD
  Skills:
  - skill{s=BossFireball} ~onTimer:100
  - skill{s=BossRoar} ~onTimer:200
  - skill{s=BossPhase2} ~onHealthBelow:50
  - effect:sound{s=ENTITY_SKELETON_DEATH} ~onDeath
  Drops:
  - BONE 10-20 1.0
  - EMERALD 1-3 0.5
  - drops:SkeletonKingTable 1 1.0
  AIGoalSelectors:
  - 0 clear
  - 1 meleeattack
  - 2 randomstroll
  AITargetSelectors:
  - 0 clear
  - 1 players
  KillMessages:
  - "&4{player} はスケルトンキングに敗北した..."
```

---

## 関連ページ

- [モブオプション](Mob-Options.md)
- [モブレベル](Mob-Levels.md)
- [モブの派閥](Mob-Factions.md)
- [装備設定](Equipment.md)
- [ボスバー](BossBar.md)
- [ダメージ修正値](Damage-Modifiers.md)
- [免疫テーブル](Immunity-Tables.md)
- [カスタムAI](Custom-AI.md)

[← ホームに戻る](../Home.md)
