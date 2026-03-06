# モブオプション (Mob Options)

モブの `Options` セクションで様々な動作を細かくカスタマイズできます。

---

## 基本構文

```yaml
MobName:
  Type: ZOMBIE
  Options:
    <オプション名>: <値>
```

---

## オプション一覧

### 移動・物理系

| オプション | 型 | デフォルト | 説明 |
|-----------|-----|-----------|------|
| `MovementSpeed` | 小数 | エンティティ依存 | 移動速度（バニラの1倍 = 約0.25） |
| `KnockbackResistance` | 小数 (0.0〜1.0) | 0.0 | ノックバック耐性（1.0 で完全無効） |
| `Gravity` | 真偽値 | true | 重力の有効化 |
| `CanSwim` | 真偽値 | true | 水泳能力 |
| `CanFly` | 真偽値 | false | 飛行能力 |
| `FlyingSpeed` | 小数 | 0.6 | 飛行速度 |

### 戦闘系

| オプション | 型 | デフォルト | 説明 |
|-----------|-----|-----------|------|
| `Damage` | 小数 | エンティティ依存 | 基本ダメージ（`Damage` フィールドと同一） |
| `NaturallyDespawn` | 真偽値 | true | 自然デスポーン |
| `Despawn` | 真偽値 | true | デスポーンを許可 |
| `PreventOtherDrops` | 真偽値 | false | バニラドロップの防止 |
| `PreventItemPickup` | 真偽値 | false | アイテム拾得の防止 |
| `PreventMobKillDrops` | 真偽値 | false | 他モブへのキルドロップ防止 |
| `PreventRenaming` | 真偽値 | false | 名前タグによるリネーム防止 |
| `PreventSlimeSplit` | 真偽値 | false | スライムの分裂防止 |

### 追跡・ターゲット系

| オプション | 型 | デフォルト | 説明 |
|-----------|-----|-----------|------|
| `FollowRange` | 整数 | エンティティ依存 | ターゲット追跡距離 |
| `AlwaysShowName` | 真偽値 | false | 名前を常に表示 |
| `HideFromPlayerList` | 真偽値 | false | プレイヤーリストから非表示 |
| `Glowing` | 真偽値 | false | グロー効果 |
| `Silent` | 真偽値 | false | 無音モード |
| `Invisible` | 真偽値 | false | 透明化 |

### エンティティ固有オプション

#### Zombie（ゾンビ）系

| オプション | 型 | デフォルト | 説明 |
|-----------|-----|-----------|------|
| `IsBaby` | 真偽値 | false | ベビーゾンビにする |

#### Creeper（クリーパー）系

| オプション | 型 | デフォルト | 説明 |
|-----------|-----|-----------|------|
| `IsPowered` | 真偽値 | false | 帯電クリーパーにする |
| `ExplosionRadius` | 整数 | 3 | 爆発半径 |
| `ExplosionFuseTime` | 整数 | 30 | 爆発までの時間（tick） |

#### Skeleton（スケルトン）系

| オプション | 型 | デフォルト | 説明 |
|-----------|-----|-----------|------|
| `IsWitherSkeleton` | 真偽値 | false | ウィザースケルトンにする |

#### Wolf（オオカミ）系

| オプション | 型 | デフォルト | 説明 |
|-----------|-----|-----------|------|
| `IsAngry` | 真偽値 | false | 怒り状態にする |
| `IsCollarColored` | 真偽値 | false | 首輪の色を設定 |
| `CollarColor` | 色 | RED | 首輪の色 |

#### Horse（馬）系

| オプション | 型 | デフォルト | 説明 |
|-----------|-----|-----------|------|
| `HorseColor` | 文字列 | WHITE | 馬の色 |
| `HorseStyle` | 文字列 | NONE | 馬の模様スタイル |
| `HorseJumpStrength` | 小数 | 0.7 | ジャンプ力 |

---

## 使用例

```yaml
BossZombie:
  Type: ZOMBIE
  Display: "&4&lボスゾンビ"
  Health: 300
  Options:
    MovementSpeed: 0.35
    KnockbackResistance: 1.0
    NaturallyDespawn: false
    Despawn: false
    PreventOtherDrops: true
    PreventItemPickup: true
    FollowRange: 50
    AlwaysShowName: true
    Silent: false
```

---

## 注意事項

- `MovementSpeed` の値はエンティティタイプによって基本値が異なります。
  - 標準的な速度は `0.2`〜`0.3` の範囲です。
  - 極端に大きな値（`1.0` 以上）を設定すると、動作が不安定になる場合があります。
- `Despawn: false` と `NaturallyDespawn: false` は別々に設定が必要な場合があります。

---

[← モブ設定に戻る](Mobs.md) | [← ホームに戻る](../Home.md)
