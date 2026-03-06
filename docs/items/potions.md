# アイテムポーション (Potions)

MythicMobsでポーションのカスタムアイテムを作成する際のオプションです。

## ポーション効果の設定

```yaml
MyPotion:
  Id: potion
  Display: '&a回復ポーション'
  PotionEffects:
  - REGENERATION 200 2    # 再生2を200ティック（10秒）
  - SATURATION 100 1      # 満腹効果を100ティック
```

## フォーマット

```yaml
PotionEffects:
- <効果タイプ> <時間（ティック）> <レベル>
```

## ポーションタイプ

| タイプ | 説明 |
|------|------|
| SPEED | 移動速度増加 |
| SLOW | 移動速度低下 |
| FAST_DIGGING | 採掘速度増加 |
| SLOW_DIGGING | 採掘速度低下 |
| INCREASE_DAMAGE | 攻撃力増加 |
| HEAL | 即時回復 |
| HARM | 即時ダメージ |
| JUMP | ジャンプ増加 |
| CONFUSION | 吐き気 |
| REGENERATION | 再生 |
| DAMAGE_RESISTANCE | 耐性 |
| FIRE_RESISTANCE | 火の耐性 |
| WATER_BREATHING | 水中呼吸 |
| INVISIBILITY | 透明化 |
| BLINDNESS | 盲目 |
| NIGHT_VISION | 暗視 |
| HUNGER | 空腹 |
| WEAKNESS | 弱体化 |
| POISON | 毒 |
| WITHER | ウィザー |
| HEALTH_BOOST | HP最大値増加 |
| ABSORPTION | 耐吸収 |
| SATURATION | 満腹 |
| GLOWING | 発光 |
| LEVITATION | 浮遊 |
| LUCK | 幸運 |
| UNLUCK | 不運 |
| SLOW_FALLING | 低速落下 |
| CONDUIT_POWER | コンジットパワー |
| DOLPHINS_GRACE | イルカの加護 |
| BAD_OMEN | 不吉な予兆 |
| HERO_OF_THE_VILLAGE | 村の英雄 |
| DARKNESS | 暗闇 |

## スプラッシュポーション

```yaml
SplashPoison:
  Id: splash_potion
  Display: '&2猛毒スプラッシュポーション'
  PotionEffects:
  - POISON 200 3   # 毒3を200ティック
  Options:
    Color: 0,200,0   # 緑色
```

## 持続ポーション

```yaml
LingeringFire:
  Id: lingering_potion
  Display: '&c炎の靄ポーション'
  PotionEffects:
  - FIRE_RESISTANCE 200 1
```
