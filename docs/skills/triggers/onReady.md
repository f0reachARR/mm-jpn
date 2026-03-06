# onReady（レディトリガー）

## 概要

モブがスポーナーからスポーンする準備ができたときにスキルを実行します。  
スポーナーから初めてスポーンする直前に一度だけ発火します。

## エイリアス

- `~onFirstSpawn`

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onReady
```

## 例

```yml
EXAMPLE_MOB:
  Type: VILLAGER
  Skills:
    # スポーナーからスポーンする準備ができたとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=READY TO SPAWN FROM A SPAWNER} @World ~onReady
    - message{m=READY TO SPAWN FROM A SPAWNER} @World ~onFirstSpawn
```

```yml
スポーナーモブ:
  Type: ZOMBIE
  Display: '&cスポーナーゾンビ'
  Health: 50
  Skills:
    # スポーナーから出現する直前にアナウンス
    - message{m="&c新たなゾンビがスポーナーから現れる！"} @World ~onReady
```

## 注意

- `~onReady` はスポーナーを使用している場合にのみ機能します。
- 手動でスポーンしたモブ（コマンドや他のメカニックによるスポーン）には発火しません。
- `~onFirstSpawn` はエイリアスであり、動作は同じです。

## 関連情報

- スポーン時 → [`~onSpawn`](onSpawn.md)
- サーバー再起動後のロード時 → [`~onLoad`](onLoad.md)
- [スポーナーの設定](/Spawners)
