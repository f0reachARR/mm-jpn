# onDeath（死亡トリガー）

## 概要

モブが死亡したときにスキルを実行します。

Paperサーバーを使用している場合、`cancelevent` メカニックを同期実行（`sync=true`）することで死亡イベントをキャンセルすることができます。  
キャンセル後のモブのHPは、`ReviveHealth` オプションで指定した値に基づきます。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**はキャスターを倒したエンティティを指します。

## 実装

- [MythicCrucible](https://git.lumine.io/mythiccraft/mythiccrucible/-/wikis/Skills/Triggers/onDeath)
- [MythicRPG](https://git.lumine.io/mythiccraft/mythicrpg/-/wikis/Skills/Triggers/onDeath)

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onDeath
```

## 例

```yml
EXAMPLE_MOB:
  Type: CHICKEN
  Skills:
    # モブが死亡したとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=DEATH} @World ~onDeath
```

```yml
# 不死身の牛の例（Paperサーバー限定）
ImmortalCow:
  Type: COW
  Display: '&e不死身の牛'
  Health: 20
  Options:
    ReviveHealth: -1
  Skills:
  - skill{s=[
    - cancelevent
    - particle{p=HEART;hs=0.5;vs=0.5;y=1.5}
    - speak{m="救急車を呼べ、ただし私のためではない！"}
    ];sync=true} @self ~onDeath
```

```yml
強力なボス:
  Type: WITHER
  Display: '&4&lダークウィザー'
  Health: 2000
  Skills:
    # 死亡時に大爆発
    - explosion{yield=10} @self ~onDeath
    # 死亡時にアナウンス
    - message{m="&4&l[!] ダークウィザーが倒された！討伐者: <trigger.name>"} @World ~onDeath
    # 死亡時に周囲のモブをスポーン
    - spawn{mob=ミニウィザー;amount=5} @self ~onDeath
```

## 注意

- `ReviveHealth: -1` を指定すると、`cancelevent` 後のHPが現在のHPと同じになります。
- `cancelevent` は必ず `sync=true` で実行してください。非同期だと機能しません。

## 関連情報

- スポーン時 → [`~onSpawn`](onSpawn.md)
- プレイヤーを倒したとき → [`~onPlayerKill`](onPlayerKill.md)
