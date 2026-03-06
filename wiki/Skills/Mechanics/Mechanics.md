# メカニクス (Mechanics)

メカニクスは、スキルが実際に実行する動作です。MythicMobs には多数のメカニクスが用意されています。

---

## 概要

```yaml
Skills:
- <メカニクス名>{<オプション>=<値>;...} @<ターゲット>
```

---

## メカニクス一覧

### ダメージ・体力系

#### damage（ダメージ）

対象にダメージを与えます。

```yaml
- damage{amount=10;ignoreArmor=false} @target
# 短縮形
- damage{a=10} @target
```

| オプション | 説明 | デフォルト |
|-----------|------|-----------|
| `amount` / `a` | ダメージ量 | 1 |
| `ignoreArmor` / `ia` | 防御力を無視するか | false |
| `preventknockback` / `pkb` | ノックバックを防止するか | false |
| `element` | ダメージ属性（カスタム） | なし |

#### heal（回復）

対象の体力を回復します。

```yaml
- heal{amount=10} @target
# 短縮形
- heal{a=10} @self
```

#### setHealth（体力設定）

対象の体力を指定値に設定します。

```yaml
- setHealth{health=100} @target
```

#### kill（即死）

対象を即座に倒します。

```yaml
- kill @target
```

---

### 移動系

#### teleport（テレポート）

対象をテレポートさせます。

```yaml
- teleport @target
- teleport{targetlocation=true} @targetLocation
```

#### pull（引き寄せ）

対象をモブの元に引き寄せます。

```yaml
- pull{velocity=1.5;yvelocity=0.5} @target
```

#### push（吹き飛ばし）

対象を吹き飛ばします。

```yaml
- push{velocity=2.0;yvelocity=1.0} @target
```

#### knockback（ノックバック）

対象をノックバックさせます。

```yaml
- knockback{power=2.0} @target
```

---

### プロジェクタイル系

#### projectile（飛翔体）

カスタム飛翔体を発射します。

```yaml
- projectile{
    onTick=ProjectileTickSkill;
    onHit=ProjectileHitSkill;
    v=3;
    i=false;
    hs=0.0;
    vs=0.0;
    timer=1;
    maxDuration=100
  } @target
```

| オプション | 説明 | デフォルト |
|-----------|------|-----------|
| `onTick` | 毎tick実行するスキル | なし |
| `onHit` | 命中時に実行するスキル | なし |
| `v` / `velocity` | 速度 | 1 |
| `i` / `interrupt` | 中断可能か | false |
| `hs` | 水平方向のスプレッド | 0 |
| `vs` | 垂直方向のスプレッド | 0 |
| `maxDuration` | 最大持続時間（tick） | 100 |

#### missile（ミサイル）

追跡型の飛翔体を発射します。

```yaml
- missile{onHit=MissileHitSkill;v=4;turnrate=10} @target
```

#### orbital（軌道体）

モブの周りを周回する飛翔体を発射します。

```yaml
- orbital{onTick=OrbitalTickSkill;onHit=OrbitalHitSkill;radius=2;duration=100} @self
```

---

### ポーション・効果系

#### potion（ポーション効果付与）

対象にポーション効果を付与します。

```yaml
- potion{t=POISON;d=100;l=1} @target
```

| オプション | 説明 | デフォルト |
|-----------|------|-----------|
| `type` / `t` | ポーション効果の種類 | SPEED |
| `duration` / `d` | 持続時間（tick） | 100 |
| `level` / `l` | 効果レベル（1から始まる） | 1 |
| `ambient` | 環境エフェクトを表示するか | false |

#### removePotion（ポーション効果除去）

対象のポーション効果を除去します。

```yaml
- removePotion{t=POISON} @target
```

#### setPotionEffect（直接適用）

ポーション効果を直接適用します（`potion` と同義）。

---

### 召喚系

#### summon（モブ召喚）

```yaml
- summon{type=Minion;amount=3;radius=3} @selfLocation
```

| オプション | 説明 | デフォルト |
|-----------|------|-----------|
| `type` | 召喚するモブ名 | なし |
| `amount` / `a` | 召喚数 | 1 |
| `radius` / `r` | 召喚半径 | 1 |
| `level` | 召喚モブのレベル | 1 |

---

### コマンド系

#### command（コマンド実行）

コマンドを実行します。

```yaml
# コンソールコマンドの実行
- command{c="say こんにちは！";sudo=console} @self

# プレイヤーとしてコマンドを実行
- command{c="gamemode creative";sudo=false} @target
```

| オプション | 説明 | デフォルト |
|-----------|------|-----------|
| `c` / `command` | 実行するコマンド | なし |
| `sudo` | 実行者（`console` / `false`） | false |

---

### メッセージ系

#### message（メッセージ送信）

対象プレイヤーにメッセージを送ります。

```yaml
- message{m="&c警告: ボスが怒り状態になった！"} @PlayersInRadius{r=50}
```

#### actionMessage（アクションバー）

アクションバー（ホットバー上部）にメッセージを表示します。

```yaml
- actionMessage{m="&cボスのHPが50%を切った！"} @PlayersInRadius{r=30}
```

#### titleMessage（タイトル）

画面中央にタイトルを表示します。

```yaml
- titleMessage{title="&cフェーズ2突入！";subtitle="&7ボスが怒り状態になった";fadein=10;stay=60;fadeout=10} @PlayersInRadius{r=30}
```

---

### スキル制御系

#### skill（外部スキル呼び出し）

別のスキルを呼び出します。

```yaml
- skill{s=AnotherSkillName} @self
```

#### delay（遅延）

指定 tick 待機します。

```yaml
- delay{d=40}     # 2秒待機
```

#### chain（スキルチェーン）

複数のスキルを順番に実行します（Skills ブロック内の複数行と同じ効果）。

---

### エフェクト系

エフェクト系メカニクスは `effect:` プレフィックスを使います。

詳細は [エフェクト](../Effects.md) を参照してください。

```yaml
- effect:particles{p=FLAME;a=30;hs=0.5;vs=0.5} @self
- effect:sound{s=ENTITY_ENDER_DRAGON_GROWL;v=1;p=1.0} @self
- effect:lightning @selfLocation
- effect:explosion{yield=0} @selfLocation
```

---

## 完全な設定例

```yaml
# Skills/BossSkills.yml

DragonBreath:
  Skills:
  - effect:particles{p=DRAGON_BREATH;a=50;hs=0.5;vs=0.5} @self
  - effect:sound{s=ENTITY_ENDER_DRAGON_GROWL;v=1;p=1.0} @self
  - projectile{
      onHit=DragonBreathHit;
      v=2;
      hs=0.1;
      vs=0.0;
      maxDuration=40
    } @forward{d=1}

DragonBreathHit:
  Skills:
  - damage{a=15;ignoreArmor=false} @EntitiesInRadius{r=2}
  - potion{t=WITHER;d=60;l=1} @EntitiesInRadius{r=2}
  - effect:particles{p=DRAGON_BREATH;a=20;hs=0.3;vs=0.3} @selfLocation

BossEnrage:
  Skills:
  - titleMessage{title="&c&l怒り状態！";subtitle="&7ボスが凶暴化した！";fadein=10;stay=60;fadeout=10} @PlayersInRadius{r=50}
  - potion{t=SPEED;d=200;l=2} @self
  - potion{t=STRENGTH;d=200;l=1} @self
  - effect:sound{s=ENTITY_ENDER_DRAGON_GROWL;v=2;p=0.5} @self
```

---

[← スキルに戻る](../Skills.md) | [← ホームに戻る](../../Home.md)
