# モブオプション (Mob Options)

モブを作成するときに使用できるすべてのオプションです。これらのほとんどのオプションは`Options`セクションに記述します：

```yml
Dummy:
  Type: skeleton
  Options:
    MovementSpeed: 0.3
    PreventSunburn: true
```

## ユニバーサルオプション

これらのオプションはモブタイプに関係なく機能します。

### AlwaysShowName

ネームタグが常に表示されるかどうか。
デフォルト: `false`

```yml
Options:
  AlwaysShowName: false
```

### AttackSpeed

モブの攻撃速度。
デフォルト: 対応するモブのバニラ攻撃速度

### VisibleByDefault

モブがスポーン時またはロード時にデフォルトで表示されるかどうか。
デフォルト: `true`

### Invisible

モブに永続的な透明効果を設定します。
デフォルト: `false`

```yml
Options:
  Invisible: true
```

### Collidable

モブが衝突判定を持つかどうか。
デフォルト: `true`

### Despawn

モブのデスポーン方法を決定します。

| モード | エイリアス | 説明 |
|------|---------|------|
| NORMAL | TRUE, YES | プレイヤーが近くにいないとデスポーン、サーバー再起動でデスポーン、チャンクアンロードでデスポーン |
| CHUNK | | サーバー再起動でデスポーン、チャンクアンロードでデスポーン |
| NEVER | FALSE, NO | 通常のmythicmobsキルコマンドで削除される |
| PERSISTENT | | チャンクアンロード時にワールドファイルにモブを保存。サーバー再起動後も維持 |
| NPC | | サーバー再起動でデスポーン、チャンクアンロードでデスポーン |

```yml
Options:
  Despawn: true
```

> PERSISTENTモードの場合: 永続モブを削除するには、`/mm m kill <type>`コマンドを使用するか、killallに`-p`フラグを追加します。

### FollowRange

モブがエンティティをターゲットにして追跡する範囲（ブロック数）。
デフォルト: `32`

```yml
Options:
  FollowRange: 32
```

### Glowing

モブが永続的に発光するかどうか。
デフォルト: `false`

### HealOnReload

チャンクがリロードされたときに非デスポーンモブをヒールするかどうか。
デフォルト: `false`

### Invincible

モブをすべてのタイプのダメージに完全に無敵にします。
デフォルト: `false`

### Interactable

モブとインタラクトできるかどうか。
デフォルト: `false`

### LockPitch

モブの頭を上下に向かせないようにします。
デフォルト: `false`

### KnockbackResistance

攻撃から抵抗するノックバックの割合。0から1の間の値。
デフォルト: `0`

```yml
Options:
  KnockbackResistance: 0.5
```

### MaxCombatDistance

指定ブロック数以上離れたプレイヤーがモブにダメージを与えることを防ぎます。
デフォルト: `256`

### MovementSpeed

モブの移動速度。
ほとんどのモブのデフォルト移動速度は`0.2`で、`1`より大きい値は戦いにくいモブになります。

```yml
Options:
  MovementSpeed: 0.2
```

### NoAI

モブにAIを持たせるかどうか。
デフォルト: `false`

### NoDamageTicks

ダメージを受けた後にモブが無敵になる時間（ティック）。
デフォルト: `10`

### NoGravity

モブに重力がないかどうか。
デフォルト: `false`

### PreventItemPickup

モブがアイテムを拾えないようにします。
デフォルト: `true`

```yml
Options:
  PreventItemPickup: false
```

### PreventLeashing

モブにリードを付けられないようにします。
デフォルト: `true`

### PreventMobKillDrops

MythicMobのターゲットのルートドロップを防ぎます。
デフォルト: `false`

### PreventOtherDrops

モブのバニラルートテーブルのドロップを防ぎます。
デフォルト: `false`

```yml
Options:
  PreventOtherDrops: false
```

### PreventRandomEquipment

モブがランダムな装備でスポーンするのを防ぎます。
デフォルト: `false`

### PreventRenaming

ネームタグを使ってモブの名前が変更されるのを防ぎます。
デフォルト: `true`

### PreventSunburn

モブが太陽で燃えるのを防ぎます。
デフォルト: `false`

```yml
Options:
  PreventSunburn: true
```

### PreventTransformation

モブが他のエンティティに変換されるのを防ぎます。
デフォルト: `true`

### RepeatAllSkills

モブがヘルス閾値以上に回復した場合に、HPベースのスキルを繰り返すかどうか。
デフォルト: `false`

### ReviveHealth

モブの死亡イベントがキャンセルされたとき、モブのHPが設定された量にリセットされます。`-1`の場合は最大HPに回復します。

```yaml
ExampleMob:
  Type: COW
  Health: 100
  Options:
    ReviveHealth: 50
  Skills:
  - cancelevent{sync=true} @self ~onDeath
```

### Scale

モブのスケール。-1に設定すると無視されます。
デフォルト: `-1`

```yaml
Options:
  Scale: 2
```

### ShowHealth

メッセージを通じてモブのHPを表示します。
デフォルト: `false`

### Silent

モブがバニラサウンドエフェクトを使用するかどうか。
デフォルト: `false`

### UseThreatTable

モブが[脅威テーブル](threat-tables.md)を使用するかどうか。

```yaml
Options:
  UseThreatTable: true
```
