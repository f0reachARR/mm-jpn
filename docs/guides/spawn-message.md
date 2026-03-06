# ガイド: スポーンメッセージ

このガイドでは、カスタムモブがスポーンしたときにサーバー全体またはプレイヤーに告知する方法を説明します。

## 基本的なスポーンメッセージ

モブのスキルに`~onSpawn`トリガーとmessageメカニクスを組み合わせて使用します：

```yaml
WorldBoss:
  Type: WITHER
  Display: '&4世界の破壊者'
  Health: 5000
  Skills:
  - skill{s=BossSpawnAnnouncement} ~onSpawn
```

```yaml
BossSpawnAnnouncement:
  Skills:
  - message{m="&4[&c警告&4] &f世界の破壊者がスポーンしました！"} @PlayersOnServer
  - message{m="&4場所: &eX:<caster.l.x> Y:<caster.l.y> Z:<caster.l.z>"} @PlayersOnServer
  - sendtitle{title="&4世界の破壊者";subtitle="&c立ち向かう準備をせよ！";fadein=10;stay=60;fadeout=10} @PlayersOnServer
```

## サウンド付きスポーンメッセージ

```yaml
BossSpawnAnnouncement:
  Skills:
  - sendtitle{title="&4WORLD BOSS";subtitle="&c倒せるものなら倒してみろ！";fadein=10;stay=80;fadeout=10} @PlayersOnServer
  - sound{sound=entity.ender_dragon.growl;volume=1;pitch=0.5} @PlayersOnServer
  - message{m="&4[&cボス&4] &f世界ボスが <caster.l.w> ワールドの X:<caster.l.x.0> Y:<caster.l.y.0> Z:<caster.l.z.0> にスポーンしました！"} @PlayersOnServer
```

## 近くのプレイヤーのみに告知

```yaml
LocalBoss:
  Type: WITHER_SKELETON
  Display: '&5地域のボス'
  Skills:
  - skill{s=LocalSpawnAnnouncement} ~onSpawn

LocalSpawnAnnouncement:
  Skills:
  - message{m="&5地域のボスが近くにスポーンしました！"} @PlayersInRadius{r=100}
```

## ボスのデス時のメッセージ

```yaml
WorldBoss:
  Type: WITHER
  Display: '&4世界の破壊者'
  Skills:
  - skill{s=BossSpawnAnnouncement} ~onSpawn
  - skill{s=BossDeathAnnouncement} ~onDeath

BossDeathAnnouncement:
  Skills:
  - message{m="&a[&2勝利&a] &f<target.name> が &4世界の破壊者 &fを倒しました！"} @PlayersOnServer
```
