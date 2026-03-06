# メタスキル (Metaskills)

[スキル](README.md)のWikiページで見たように、モブから以下の構文でメカニクスを実行することが可能です：

```yaml
- mechanic{argument=value} @[targeter] ~on[trigger] [health_modifier] [chance]
```

しかし、このアプローチは複数のメカニクスを「グループ化」したい場合や、モブのより高度な動作を作成したい場合には適していません。これはメタスキルを使用することで解決できます。

## メタスキルとは？

メタスキルは、[メタメカニクス]によってメタスキルが呼び出されると実行されるメカニクスのリストです。
**`../plugins/MythicMobs/Skills`内の`.yml`ファイルに配置されます。**

メタスキルの構文は以下の通りです：

```yaml
internal_skillname:
  CancelIfNoTargets: [true/false]
  Conditions:
  - condition1
  - condition2
  TargetConditions:
  - condition3
  TriggerConditions:
  - condition5
  FailedConditionsSkill: [条件が満たされない場合に実行するメタスキル]
  Cooldown: [seconds]
  OnCooldownSkill: [クールダウン中に実行するメタスキル]
  Skill: [非同期で実行する追加のメタスキル]
  Skills:
  - mechanic1
  - mechanic2
```

メタスキルを設定したら、[Skill]などの[メタメカニクス]を使用して、モブまたはメタスキルからメタスキルを実行できます：

```yaml
# MOBファイル
ExampleMob:
  Type: ZOMBIE
  Skills:
  - skill{s=internal_skillname} @self ~onInteract
```

## 各設定の説明

### CancelIfNoTargets

適格なターゲットが提供されない場合に、メタスキルの実行をキャンセルするかどうか。
デフォルト: `true`

### Conditions

メタスキルのコンディション。これらの条件はメタスキルのキャスターに対して評価されます。

### TargetConditions

ターゲットコンディション。これらの条件はメタスキルの継承されたターゲットに対して評価されます。

### TriggerConditions

トリガーコンディション。これらの条件はスキルツリーをトリガーしたエンティティに対して評価されます。

### FailedConditionsSkill（エイリアス: OnFailSkill）

コンディションが満たされない場合に実行されるメタスキル。

```yaml
ExampleSkill:
  Conditions:
  - day true
  OnFailSkill: ExampleSkill2

ExampleSkill2:
  Skills:
  - message{m="どうやら昼間ではないようです。"} @World
```

### Cooldown

クールダウンは、同じキャスターによるメタスキルの実行間隔（秒）です。

```yaml
ExampleCooldownSkill:
  Cooldown: 10
  Skills:
  - ignite @self
```

### OnCooldownSkill

メタスキルがクールダウン中にトリガーされた場合、代わりにここで指定されたスキルがキャストされます。

### Skills

メタスキルのコア。トリガーされたときにメタスキルによって実行されるメカニクスのリストです。

```yaml
ExampleSkill:
  Skills:
  - message{m="こんにちは！"}
  - delay 20
  - message{m="調子はいかがですか？"}
```

## ターゲットの継承とオーバーライド

### 継承

ターゲッターを持たないメタスキル内のメカニクスは、渡されたターゲットを**継承**します。

```yaml
# MOBファイル
ExampleMob:
  Type: ZOMBIE
  Skills:
  - skill{s=ExampleSkill} @PIR{r=10} ~onInteract
```

```yaml
# スキルファイル
ExampleSkill:
  Skills:
  - ignite  # ターゲッターなし - 10ブロック半径内のすべてのプレイヤーに適用
```

### オーバーライド

メタスキル内にターゲッターが指定されている場合、元のターゲッターは**オーバーライド**されます。

```yaml
ExampleSkill:
  Skills:
  - ignite              # 継承されたターゲット（半径10m内のプレイヤー）に火をつける
  - message{m="接近しすぎです！"} @NearestPlayer{r=1}  # 最も近いプレイヤーにメッセージ
```

## 例

### 基本的なメタスキルの例

```yaml
# MOBファイル
SkeletalBoss:
  Type: SKELETON
  Skills:
  - skill{s=FireArrow_Skill} @target ~onAttack
  - skill{s=AOEIce_Skill} ~onTimer:200 0.3

# スキルファイル
FireArrow_Skill:
  Skills:
  - ignite{ticks=60} @trigger
  - sound{sound=entity.arrow.hit_player} @trigger

AOEIce_Skill:
  Cooldown: 10
  Skills:
  - effect:particles{p=SNOWBALL;amount=100;radius=5} @self
  - potioneffect{type=SLOWNESS;d=100;l=2} @PlayersInRadius{r=5}
  - message{m="凍えろ！"} @PlayersInRadius{r=10}
```
