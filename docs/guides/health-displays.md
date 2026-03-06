# ガイド: ヘルス表示

このガイドでは、さまざまな方法でモブのHPをプレイヤーに表示する方法を説明します。

## 方法1: ビルトインのShowHealthオプション

最も簡単な方法は`ShowHealth`オプションを使用することです：

```yaml
MyMob:
  Type: ZOMBIE
  Options:
    ShowHealth: true
```

`config.yml`でフォーマットをカスタマイズできます：

```yaml
Mobs:
  ShowHealth:
    Radius: 30
    Formatting: "&cHP: <hp>/<maxhp>"
```

## 方法2: アクションバーでのHP表示

スキルを使ってアクションバーにHPを表示します：

```yaml
HealthBarMob:
  Type: ZOMBIE
  Display: '&4フォレストデーモン'
  Health: 500
  Skills:
  - skill{s=ShowHealthBar} ~onTimer:5
  - skill{s=RemoveHealthBar} @trigger ~onDeath

ShowHealthBar:
  Skills:
  - sendactionbar{m="&4フォレストデーモン &c<caster.php>%HP"} @PlayersInRadius{r=30}

RemoveHealthBar:
  Skills:
  - sendactionbar{m=""} @PlayersInRadius{r=30}
```

## 方法3: ホログラムによるHP表示

ホログラムを使ってモブのHP表示を作成します：

```yaml
HologramBoss:
  Type: ZOMBIE
  Display: '&4ホログラムボス'
  Health: 1000
  Skills:
  - skill{s=UpdateHologram} ~onSpawn
  - skill{s=UpdateHologram} ~onTimer:10

UpdateHologram:
  Skills:
  - hologram{text="&4ホログラムボス\n&c<caster.hp>/<caster.mhp>";d=2;y=2.5} @SelfLocation
```

## 方法4: タイトルでのHP表示（ダメージを受けたとき）

ダメージを受けたときにのみプレイヤーにHPを表示します：

```yaml
BossWithDamageIndicator:
  Type: ZOMBIE
  Display: '&4ボス'
  Health: 1000
  Skills:
  - skill{s=ShowDamageHP} @trigger ~onDamaged

ShowDamageHP:
  Skills:
  - sendtitle{title="&4ボスHP";subtitle="&c<caster.php>% (&a<caster.hp>/<caster.mhp>)";fadein=0;stay=30;fadeout=10} @trigger
```

## 方法5: ボスバーでのHP表示

最も視覚的に優れた方法は、ボスバーを使用することです：

```yaml
BossWithBar:
  Type: ZOMBIE
  Display: '&4エピックボス'
  Health: 1000
  BossBar:
    Enabled: true
    Title: '&4エピックボス'
    Range: 40
    Color: RED
    Style: NOTCHED_20
```
