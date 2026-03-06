# onSpawnOrLoad（スポーン・ロードトリガー）

## 概要

[`~onSpawn`](onSpawn.md) または [`~onLoad`](onLoad.md) のいずれかが発火する状況でスキルを実行します。  
モブが初めてスポーンするときと、サーバー再起動後にロードされるときの両方に対応します。

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onSpawnOrLoad
```

## 例

```yml
EXAMPLE_MOB:
  Type: VILLAGER
  Skills:
    # モブがスポーンしたとき、またはサーバー再起動後にロードされたとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m="SPAWNED! Or was i loaded?"} @World ~onSpawnOrLoad
```

```yml
持続型ガーディアン:
  Type: GUARDIAN
  Display: '&3守護者'
  Health: 300
  Options:
    Persistent: true
  Skills:
    # スポーン・ロードのいずれのときもバフを付与
    - potion{t=WATER_BREATHING;d=99999;l=1} @self ~onSpawnOrLoad
    - potion{t=INCREASE_DAMAGE;d=99999;l=1} @self ~onSpawnOrLoad
    # スポーン・ロード時にアナウンス
    - message{m="&3守護者が現れた！"} @World ~onSpawnOrLoad
```

## 注意

- `~onSpawnOrLoad` は `~onSpawn` と `~onLoad` の両方をまとめて処理できる便利なトリガーです。
- 初期化処理（バフの付与、データの設定など）に特に有効です。

## 関連情報

- スポーン時のみ → [`~onSpawn`](onSpawn.md)
- ロード時のみ → [`~onLoad`](onLoad.md)
