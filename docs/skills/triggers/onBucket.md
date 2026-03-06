# onBucket（バケツトリガー）

## 概要

牛がミルクされたとき、またはアクソロートルなどのバケツに入れられるエンティティがバケツに入れられたときにスキルを実行します。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**はキャスター自身を指します。

## エイリアス

- `~onUseBucket`
- `~onFillBucket`
- `~onBucketFill`
- `~onMilk`
- `~onMilked`

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onBucket
```

## 例

```yml
ANormalCow:
  Type: Cow
  Skills:
  - skill{s=[
    - message{m="HOW DARE YOU?!?"} @trigger
    - sound{s=entity.creeper.primed}
    - explosion{yield=5;delay=30}
    ];cd=2} @self ~onBucket
```

```yml
激怒する牛:
  Type: COW
  Display: '&c激怒する牛'
  Health: 50
  Skills:
    # バケツを使われたとき（ミルクされたとき）にメッセージ
    - message{m="&c[牛] なんてことするんだ！！"} @trigger ~onBucket
    # バケツを使ったプレイヤーに攻撃
    - damage{a=10} @trigger ~onBucket
    # サウンドを再生
    - sound{s=entity.cow.hurt;v=2} @self ~onBucket
    # パーティクルを表示
    - particle{p=CRIT;amount=15;hs=0.5;vs=0.5} @self ~onBucket
```

```yml
魔法のアクソロートル:
  Type: AXOLOTL
  Display: '&b魔法のアクソロートル'
  Health: 15
  Skills:
    # バケツに入れられたとき
    - message{m="&b[アクソロートル] 狭い！解放して！"} @trigger ~onBucket
    - potion{t=NAUSEA;d=60;l=1} @trigger ~onBucket
```

## 注意

- 牛（COW）の場合は `~onMilk` や `~onMilked` というエイリアスが特に分かりやすいです。
- バケツ対応エンティティ：アクソロートル、コッドフィッシュ、サーモン、トロピカルフィッシュ、プファーフィッシュ、タッドポールなど。

## 関連情報

- インタラクト時 → [`~onInteract`](onInteract.md)
