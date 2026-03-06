# エフェクト (Effects)

エフェクトは視覚・音響効果を表現するためのメカニクスです。`effect:` プレフィックスを使用します。

---

## 概要

```yaml
Skills:
- effect:<エフェクト名>{<オプション>} @<ターゲット>
```

---

## エフェクト一覧

### particles（パーティクル）

パーティクル効果を生成します。

```yaml
- effect:particles{p=FLAME;a=30;hs=0.5;vs=0.5;s=0.1;force=false} @self
```

| オプション | 説明 | デフォルト |
|-----------|------|-----------|
| `particle` / `p` | パーティクルの種類 | FLAME |
| `amount` / `a` | パーティクルの数 | 20 |
| `hSpread` / `hs` | 水平方向の広がり | 0.5 |
| `vSpread` / `vs` | 垂直方向の広がり | 0.5 |
| `speed` / `s` | パーティクルの速度 | 0 |
| `force` | 表示範囲を強制するか | false |

主なパーティクル種別：

| パーティクル名 | 見た目 |
|-------------|--------|
| `FLAME` | 炎 |
| `SMOKE_NORMAL` | 煙 |
| `SMOKE_LARGE` | 大きな煙 |
| `EXPLOSION_NORMAL` | 爆発（小） |
| `EXPLOSION_LARGE` | 爆発（大） |
| `EXPLOSION_HUGE` | 爆発（特大） |
| `HEART` | ハート |
| `VILLAGER_HAPPY` | 村人の幸せ |
| `CRIT` | クリティカル |
| `MAGIC_CRIT` | 魔法クリティカル |
| `ENCHANTMENT_TABLE` | エンチャントテーブル |
| `SPELL_MOB` | モブのスペル |
| `DRAGON_BREATH` | ドラゴンブレス |
| `END_ROD` | エンドロッド |
| `FIREWORKS_SPARK` | 花火 |
| `WATER_SPLASH` | 水しぶき |
| `PORTAL` | ポータル |
| `REDSTONE` | 赤石（色指定可能） |
| `SNOWFLAKE` | 雪片 |
| `ELECTRIC_SPARK` | 電撃 |
| `SCRAPE` | 削り |

---

### sound（サウンド）

効果音を再生します。

```yaml
- effect:sound{s=ENTITY_ENDER_DRAGON_GROWL;v=1.0;p=1.0} @self
```

| オプション | 説明 | デフォルト |
|-----------|------|-----------|
| `sound` / `s` | サウンド名（Bukkit サウンド名） | ENTITY_PLAYER_HURT |
| `volume` / `v` | 音量（0.0〜2.0） | 1.0 |
| `pitch` / `p` | ピッチ（0.5〜2.0） | 1.0 |

主なサウンド名の例：

| サウンド名 | 説明 |
|-----------|------|
| `ENTITY_ENDER_DRAGON_GROWL` | エンダードラゴンの咆哮 |
| `ENTITY_ENDER_DRAGON_HURT` | エンダードラゴンの被ダメージ音 |
| `ENTITY_WITHER_SPAWN` | ウィザー召喚音 |
| `ENTITY_LIGHTNING_BOLT_THUNDER` | 雷の音 |
| `ENTITY_GENERIC_EXPLODE` | 爆発音 |
| `ENTITY_PLAYER_HURT` | プレイヤーの被ダメージ音 |
| `BLOCK_NOTE_BLOCK_PLING` | ノートブロック音 |
| `ITEM_SHIELD_BLOCK` | シールドのブロック音 |

---

### lightning（落雷）

落雷エフェクトを生成します（ダメージなし）。

```yaml
- effect:lightning @targetLocation
```

---

### lightningStrike（雷撃）

実際にダメージを与える落雷を生成します。

```yaml
- effect:lightningStrike @targetLocation
```

---

### explosion（爆発）

爆発エフェクトを生成します。

```yaml
- effect:explosion{yield=0;fire=false} @targetLocation
```

| オプション | 説明 | デフォルト |
|-----------|------|-----------|
| `yield` | 爆発の大きさ（0=ブロック破壊なし） | 0 |
| `fire` | 爆発後に炎を生成するか | false |

---

### firework（花火）

花火を打ち上げます。

```yaml
- effect:firework{
    power=1;
    type=BALL;
    primary=RED,YELLOW;
    fade=WHITE;
    flicker=true;
    trail=true
  } @selfLocation
```

| オプション | 説明 |
|-----------|------|
| `power` | 打ち上げ高さ |
| `type` | 花火タイプ（BALL / BALL_LARGE / STAR / BURST / CREEPER） |
| `primary` | メイン色（カンマ区切り複数指定可） |
| `fade` | フェードアウト色 |
| `flicker` | チカチカエフェクト |
| `trail` | 軌跡エフェクト |

---

### block（ブロックエフェクト）

ブロック破壊パーティクルを生成します。

```yaml
- effect:block{m=STONE} @selfLocation
```

---

### item（アイテムエフェクト）

アイテムのパーティクルを生成します。

```yaml
- effect:item{i=DIAMOND} @self
```

---

### particleLine（パーティクルライン）

2点間にパーティクルの線を引きます。

```yaml
- effect:particleLine{p=FLAME;a=5;s=0.0} @self ~onTimer:20
```

---

### particleOrbit（パーティクルオービット）

モブの周りにパーティクルの軌道を作ります。

```yaml
- effect:particleOrbit{p=FLAME;radius=2;duration=100;yoffset=1} @self
```

---

## 設定例

```yaml
# 完全なボス演出

BossIntroEffect:
  Skills:
  # ドラゴンの咆哮
  - effect:sound{s=ENTITY_ENDER_DRAGON_GROWL;v=2;p=0.5} @self
  # 雷効果
  - effect:lightning @selfLocation
  # 爆発エフェクト
  - effect:explosion{yield=0} @selfLocation
  # 大量のパーティクル
  - effect:particles{p=DRAGON_BREATH;a=100;hs=1.0;vs=1.0} @self
  # タイトルメッセージ
  - titleMessage{title="&5&lドラゴン覚醒！";fadein=20;stay=60;fadeout=20} @PlayersInRadius{r=50}
  # 花火
  - effect:firework{power=2;type=BALL_LARGE;primary=PURPLE,RED;flicker=true} @selfLocation
```

---

[← スキルに戻る](../Skills.md) | [← ホームに戻る](../../Home.md)
