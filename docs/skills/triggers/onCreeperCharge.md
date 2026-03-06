# onCreeperCharge（クリーパー帯電トリガー）

## 概要

クリーパーが帯電（チャージ）したときにスキルを実行します。  
クリーパーへの落雷によって帯電状態になったときに発火します。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**はキャスター自身を指します。

## エイリアス

- `~onCreeper_Charge`
- `~onCharged`
- `~onCharge`

## 使い方

```yml
モブ名:
  Type: CREEPER
  Skills:
    - <メカニック> ~onCreeperCharge
```

## 例

```yml
EXAMPLE_MOB:
  Type: CREEPER
  Skills:
    # クリーパーが帯電したとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=CHARGED} @World ~onCreeperCharge
```

```yml
帯電クリーパー:
  Type: CREEPER
  Display: '&e&l帯電クリーパー'
  Health: 25
  Skills:
    # 帯電時に警告アナウンス
    - message{m="&e&l[!] 帯電クリーパーが出現！より強力な爆発が来るぞ！"} @World ~onCreeperCharge
    # 帯電時にサウンドを再生
    - sound{s=entity.lightning_bolt.thunder;v=2;pi=1} @World ~onCreeperCharge
    # 帯電時にパーティクルを表示
    - particle{p=END_ROD;amount=30;hs=0.5;vs=1} @self ~onCreeperCharge
    # 帯電時にHPを増加
    - sethealth{h=40} @self ~onCreeperCharge
```

## 注意

- このトリガーはクリーパー（CREEPER）タイプのモブにのみ機能します。
- 帯電クリーパーの爆発は通常より強力で、爆発範囲が広くなります。

## 関連情報

- 起爆準備時 → [`~onPrime`](onPrime.md)
- 爆発時 → [`~onExplode`](onExplode.md)
