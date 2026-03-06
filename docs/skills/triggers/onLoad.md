# onLoad（ロードトリガー）

## 概要

サーバーの再起動後にモブがロードされたときにスキルを実行します。  
MythicMobs はサーバー再起動をまたいでモブを永続させる機能を持っており、そのロード時にこのトリガーが発火します。

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onLoad
```

## 例

```yml
EXAMPLE_MOB:
  Type: VILLAGER
  Skills:
    # サーバー再起動後にモブがロードされたとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=LOADED} @World ~onLoad
```

```yml
持続ボス:
  Type: ELDER_GUARDIAN
  Display: '&b&l守護者ボス'
  Health: 500
  Options:
    PreventOtherDrops: true
    Persistent: true
  Skills:
    # ロード時にアナウンス
    - message{m="&b守護者がサーバー再起動から復活した！"} @World ~onLoad
    # ロード時にバフを再適用
    - potion{t=WATER_BREATHING;d=99999;l=1} @self ~onLoad
```

## 注意

- `~onLoad` はサーバーの再起動（またはチャンクのロード）によってモブが再び読み込まれたときに発火します。
- 初回スポーンには発火しません。初回スポーンには `~onSpawn` を使用してください。
- スポーンとロードの両方をカバーしたい場合は `~onSpawnOrLoad` を使用してください。

## 関連情報

- スポーン時 → [`~onSpawn`](onSpawn.md)
- スポーンまたはロード時 → [`~onSpawnOrLoad`](onSpawnOrLoad.md)
