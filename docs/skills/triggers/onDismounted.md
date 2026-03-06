# onDismounted（降車トリガー）

## 概要

モブから降りた（降車した）ときにスキルを実行します。

## エイリアス

- `~onUnmounted`

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onDismounted
```

## 例

```yml
EXAMPLE_MOB:
  Type: HORSE
  Skills:
    # 降車したプレイヤーにメッセージを送信し、70%の確率で降車をキャンセルする
    - skill{s=[
      - cancelevent
      - message{m=Going somewhere?} @trigger
     ];sync=true} @self ~onDismounted 0.7
```

```yml
呪われた馬:
  Type: HORSE
  Display: '&5呪われた馬'
  Health: 100
  Options:
    Invincible: true
  Skills:
    # 降車しようとしたとき
    - skill{s=[
      - cancelevent
      - message{m="&5[馬] おっと、降りることは許さん！"} @trigger
      - potion{t=WEAKNESS;d=100;l=1} @trigger
      ];sync=true} @self ~onDismounted
```

```yml
乗れる牛:
  Type: COW
  Display: '&aライドカウ'
  Health: 50
  Skills:
    # 降りたプレイヤーにお礼メッセージ
    - message{m="&a[牛] 乗ってくれてありがとう！またね！"} @trigger ~onDismounted
    # 降りたプレイヤーに加速効果を付与
    - potion{t=SPEED;d=60;l=2} @trigger ~onDismounted
    # 降車時にパーティクル演出
    - particle{p=HEART;amount=5;hs=0.5;vs=0.5} @self ~onDismounted
```

## 注意

- `cancelevent` を使用することで降車をキャンセルすることができます。ただし、必ず `sync=true` で実行してください。
- 確率を指定することで（例：`0.7` = 70%の確率）、降車をランダムにキャンセルする演出も可能です。
- `@trigger` を使用することで、降りたプレイヤーを対象にできます。

## 関連情報

- インタラクト時 → [`~onInteract`](onInteract.md)
- スポーン時 → [`~onSpawn`](onSpawn.md)
