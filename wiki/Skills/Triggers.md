# トリガー (Triggers)

トリガーは、スキルが発動するタイミングを指定します。

---

## 概要

```yaml
Skills:
- <スキル> ~<トリガー>[:<値>]
```

---

## トリガー一覧

### タイマー系

| トリガー | 説明 |
|---------|------|
| `~onTimer:<tick>` | 指定 tick（1tick = 1/20秒）ごとに繰り返し発動 |

**例**:
```yaml
- skill{s=MySkill} ~onTimer:100    # 5秒（100tick）ごとに発動
- skill{s=MySkill} ~onTimer:20     # 1秒（20tick）ごとに発動
```

---

### スポーン・死亡系

| トリガー | 説明 |
|---------|------|
| `~onSpawn` | モブがスポーンした時に1回発動 |
| `~onDeath` | モブが死亡した時に発動 |
| `~onDespawn` | モブがデスポーンした時に発動 |

---

### 戦闘系

| トリガー | 説明 |
|---------|------|
| `~onAttack` | モブが攻撃を行った時に発動 |
| `~onDamaged` | モブがダメージを受けた時に発動 |
| `~onKill` | エンティティを倒した時に発動 |
| `~onKillPlayer` | プレイヤーを倒した時に発動 |
| `~onCombat` | 戦闘状態になった時に発動 |
| `~onEnterCombat` | 戦闘開始時に1回発動 |
| `~onLeaveCombat` | 戦闘終了時に発動 |
| `~onChangeTarget` | ターゲットが変わった時に発動 |
| `~onTeleport` | テレポートした時に発動 |

---

### 体力系

| トリガー | 説明 |
|---------|------|
| `~onHealthBelow:<パーセント>` | 体力が指定パーセント以下になった時に1回発動 |
| `~onHealthAbove:<パーセント>` | 体力が指定パーセント以上になった時に1回発動 |

**例**:
```yaml
- skill{s=Phase2} ~onHealthBelow:50     # HP50%以下で発動
- skill{s=Enrage} ~onHealthBelow:25     # HP25%以下で発動
```

---

### インタラクション系

| トリガー | 説明 |
|---------|------|
| `~onInteract` | プレイヤーが右クリックした時に発動 |
| `~onShoot` | スケルトン等が矢を射る時に発動 |

---

### 環境系

| トリガー | 説明 |
|---------|------|
| `~onBlockBreak` | ブロックを壊した時に発動 |
| `~onExplode` | 爆発した時に発動（クリーパー等） |

---

## 複数トリガーの組み合わせ

複数のトリガーを持つスキルは、別々の行として定義します：

```yaml
DragonBoss:
  Skills:
  # スポーン時に演出
  - effect:sound{s=ENTITY_ENDER_DRAGON_GROWL} @self ~onSpawn
  # 5秒ごとにファイアボール
  - projectile{...} @target ~onTimer:100
  # HP50%以下でフェーズ2スキル
  - skill{s=Phase2} ~onHealthBelow:50
  # 死亡時に爆発
  - effect:explosion{power=3} @self ~onDeath
  # ダメージ時に咆哮
  - effect:sound{s=ENTITY_ENDER_DRAGON_HURT;v=1;p=0.5} @self ~onDamaged
```

---

## tick の目安

| tick数 | 時間 |
|--------|------|
| 1 | 約0.05秒 |
| 10 | 0.5秒 |
| 20 | 1秒 |
| 40 | 2秒 |
| 60 | 3秒 |
| 100 | 5秒 |
| 200 | 10秒 |
| 400 | 20秒 |
| 1200 | 60秒（1分） |

---

## 注意事項

- `~onHealthBelow` と `~onHealthAbove` は一度発動すると、体力が回復して再び条件を満たしても発動しません（1回のみ）。
- `~onTimer` は モブがアクティブな状態（プレイヤーが近くにいる）のときのみカウントされます。
- `~onSpawn` はコマンドでスポーンした場合も発動します。

---

[← スキルに戻る](Skills.md) | [← ホームに戻る](../Home.md)
