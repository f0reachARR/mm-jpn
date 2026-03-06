# モブ (Mobs)

MythicMobsはカスタマイズされたエンティティ/モブを中心に構築されており、カスタム作成物に利用できる多くのオプションや属性があります。

ほとんどのオプションはオプション（任意）であり、新しいモブを作成するたびにリスト全体を設定する必要はありません。実際に必要なのは`内部名（Internal_Name）`と`タイプ（Type）`だけです。

## 目次

- [モブ設定の詳細](#モブ設定の詳細)
- [例](#例)
- [サブページ](#サブページ)

## モブ設定の詳細

### 内部名（Internal_Name）

この文字列はMythicMobs内でモブを参照する方法で、任意の名前を使用できます。
ユニークな名前である必要があり、他の内部モブ名と衝突しないでください。**スペースは使用不可**。

```yml
example_name:
```

### タイプ（Type）

このフィールドは、作成物のベースとなるエンティティタイプを決定します。
利用可能な[エンティティタイプ](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/entity/EntityType.html)の完全なリストはSpigot Javadocsで、[こちら](types.md)で明示的に実装されているタイプのリストを見つけることができます。

> Minecraftがゲームに追加する新しいエンティティタイプのいくつかのモブオプションは、Mythicがそのエンティティタイプのサポートを追加するまで機能しません。

```yml
example_mob:
  Type: zombie
```

### 表示名（Display）

モブの表示名を設定します。
このオプションはカラーコードと[プレースホルダー](../skills/placeholders.md)をサポートします。

**モブの名前はそれ自体では変更・更新されません。[setname](../skills/mechanics/setname.md)メカニクスを使って変更・更新する必要があります。**

```yml
example_mob:
  Type: zombie
  Display: サンプルモブ
```

### HP（Health）

モブの最大HPのベース値を設定します。
MythicMobsは最大HPに制限はありませんが、Spigotが`2048`で最大HPをキャップします。
これはSpigotの設定ファイル`server_root\spigot.yml`で簡単に変更できます。

```yml
example_mob:
  Type: zombie
  Display: サンプルモブ
  Health: 30
```

### 攻撃力（Damage）

モブの近接攻撃ダメージのベース値を設定します。
1ダメージは0.5ハートに等しいため、6ダメージのモブは3ハートのダメージを与えます。
この属性は矢やポーションなどの遠距離攻撃によるダメージには影響しません。

```yml
example_mob:
  Type: zombie
  Display: サンプルモブ
  Damage: 20
```

### アーマー（Armor）

モブのアーマー属性のベース値を設定します。
Minecraftは最大アーマー値を30にキャップします。

```yml
example_mob:
  Type: zombie
  Display: タンカー
  Armor: 25
```

### HPバー（HealthBar）

モブの上にシンプルなHPバーホログラムを作成します（モブがダメージを受けた後）。

```yml
example_mob:
  Type: zombie
  Display: ヘルシーボーイ
  Health: 1000
  HealthBar:
    Enabled: true
    Offset: 1.45
```

### ボスバー（BossBar）

モブのボスバーを定義・制御します。
エンダードラゴンやウィザーのボスバーに似ていますが、外観を設定できます。
[BossBar](bossbar.md)を参照してください。

```yml
example_mob:
  Type: zombie
  Armor: 25
  BossBar:
    Enabled: true
    Title: タンカー
    Range: 20
    Color: RED
    Style: NOTCHED_6
    CreateFog: true
    DarkenSky: true
    PlayMusic: true
```

### ファクション（Faction）

モブのファクションを設定します。これはカスタムAI設定やターゲッターフィルタリングに使用できます。
ファクションは大文字小文字を区別するので、ファクション条件を使用する際は注意してください。

```yml
example_mob:
  Type: zombie
  Armor: 25
  Faction: タンク
```

### マウント（Mount）

モブのマウントを設定します。
別のMythicMobでなければなりません。
モブはスポーン時に定義されたマウントに自動的に乗ります。

```yml
another_example:
  Type: chicken
  Mount: example_mob
```

### オプション（Options）

モブが消滅しないかどうか、ノックバック耐性、フォローレンジ、移動速度など、多数のサブオプションを持つ特別なフィールドです。
利用可能なモブオプションのリストは[モブオプション](options.md)ページにあります。

```yml
slow_persistent_mob:
  Type: husk
  Options:
    MovementSpeed: 0.025
    Despawn: PERSISTENT
```

### モジュール（Modules）

このフィールドにより、[脅威テーブル](threat-tables.md)や[免疫テーブル](immunity-tables.md)などのモジュールを有効/無効にできます。

```yml
example_mob:
  Type: husk
  Modules:
    ThreatTable: false
    ImmunityTable: false
```

### AIゴールセレクター（AIGoalSelectors）

モブの[AIゴール](custom-ai.md)を変更・カスタマイズします。

```yml
dummy_mob:
  Type: zombie
  AIGoalSelectors:
    - clear
```

### AIターゲットセレクター（AITargetSelectors）

モブの[AIターゲット](custom-ai.md)を変更・カスタマイズします。

```yml
neutral_mob:
  Type: zombie
  AIGoalSelectors:
    - clear
    - meleeattack
    - randomstroll
    - randomlookaround
  AITargetSelectors:
    - clear
    - attacker
```

### ドロップ（Drops）

モブのルートドロップを追加または完全に変更します。
バニラアイテム、Mythicアイテム、経験値、プラグイン間アイテム（サポートされている場合）、または独自の条件システムを持つカスタムドロップテーブルにできます。
詳細は[ドロップ＆ドロップテーブル](../drops/README.md)を参照してください。

```yml
example_mob:
  Type: zombie
  Options:
    PreventOtherDrops: true
  Drops:
    - diamond 32 1
    - netherite_ingot 12 0.5
```

### ダメージ修飾子（DamageModifiers）

異なるダメージ原因からモブが受けるダメージ量を変更します。
詳細は[ダメージ修飾子](damage-modifiers.md)を参照してください。

```yml
example_mob:
  Type: zombie
  DamageModifiers:
    - ENTITY_ATTACK 0
    - PROJECTILE 1.25
```

### 装備（Equipment）

初めてスポーンする際にモブにバニラアイテムやMythicアイテムを装備させます。
詳細は[装備](equipment.md)を参照してください。

```yml
example_mob:
  Type: zombie
  Options:
    PreventRandomEquipment: true
  Equipment:
    - diamond_sword HAND
    - diamond_helmet{name=<green>COMMON</green> ヘルメット} HEAD
```

### キルメッセージ（KillMessages）

モブがプレイヤーを倒したときに表示される[キルメッセージ](kill-messages.md)をカスタマイズします。

```yml
example_mob:
  Type: zombie
  Display: タンカー
  KillMessages:
    - <caster.name>が<target.name>をぶっ飛ばした！
    - お前は弱すぎる、<target.name>！
```

### レベル修飾子（LevelModifiers）

MythicMobsは[レベル](levels.md)を持つことができ、このフィールドはレベルが変化したときにどのような統計を得るべきかを決定するために使用します。

```yml
example_mob:
  Type: zombie
  Display: ダミー
  LevelModifiers:
    Damage: 2
    Health: 0.25
```

### ディスガイズ（Disguise）

モブの外観を他のエンティティタイプのように変更します。
サーバーに[LibsDisguises](https://www.spigotmc.org/resources/libs-disguises-free.81/)がインストールされ機能している必要があります。
詳細は[ディスガイズ](disguises.md)を参照してください。

```yml
# このモブはゾンビとして動作しますが、チキンのように見えます
example_mob:
  Type: zombie
  Disguise: chicken
```

### スキル（Skills）

スキルはMythicの重要な機能です。すべてのモブは、異なる状況でさまざまな条件で発動できるさまざまなタイプのスキルを持つことができます。
詳細は[スキル](../skills/README.md)を参照してください。

```yml
# 右クリックしたプレイヤーとの位置を交換します
example_mob:
  Type: zombie
  Skills:
    - swap @trigger ~onInteract
```

### ネームプレート（Nameplate）

`Enabled: true`オプションが使用されている場合、モブにMythicネームプレートの使用を強制します。

```yaml
ExampleMob:
  Type: PIG
  Display: "Hello\nWorld!"
  Nameplate:
    Enabled: true
    Offset: 1.8
    Scale: 1,1,1
    Mounted: true
```

### ヒアリング（Hearing）

モブがウォーデンのように音を「聞く」ことを可能にします。

```yaml
ICanHearYou:
  Type: ZOMBIE
  Hearing:
    Enabled: true
  Skills:
  - message{m="<trigger.name>の声が聞こえる！"} @trigger ~onHear
```

### 変数（Variables）

スポーン時にすでに設定された[変数](../skills/variables.md)を使ってモブをスポーンさせることができます。

```yaml
VariableZombie:
  Type: ZOMBIE
  Variables:
    SomeVariable: something
    AnIntVariable: int/2
    AFloatVariable: float/420.69
```

### 取引（Trades）

村人の取引をカスタマイズします。
村人はカスタム取引を維持するために職業とレベル2以上の職業レベルを持つ必要があります。

```yml
MerchantTest:
  Type: VILLAGER
  Display: '&6商人テスト'
  Options:
    Profession: CLERIC
    Type: DESERT
    Level: 2
  Trades:
    1:
      Item1: 5 EMERALD
      Item2: 5 DIAMOND
      Result: DIAMOND_SWORD
    2:
      Item1: 64 EMERALD
      Result: mmoitems.SWORD.CUTLASS
      MaxUses: 1
```

## サブページ

- [モブオプション](options.md)
- [表示オプション](display-options.md)
- [マネキンオプション](mannequin-options.md)
- [モブレベル](levels.md)
- [モブファクション](factions.md)
- [ボスバー](bossbar.md)
- [ダメージ修飾子](damage-modifiers.md)
- [装備](equipment.md)
- [ディスガイズ](disguises.md)
- [カスタムAI](custom-ai.md)
- [キルメッセージ](kill-messages.md)
- [脅威テーブル](threat-tables.md)
- [免疫テーブル](immunity-tables.md)
- [テンプレート](templates.md)
- [タイプ](types.md)
- [パワーレベル](power-level.md)
