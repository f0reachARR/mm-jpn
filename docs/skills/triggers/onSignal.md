# onSignal（シグナルトリガー）

## 概要

モブが [signal メカニック](/Skills/Mechanics/Signal) からシグナルを受信したときにスキルを実行します。

**特殊な構文：** `~onSignal:<シグナル名>`

- シグナル名は英数字のみ使用できます。
- シグナル名を省略すると、どのシグナルを受信しても発火します。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**はシグナルを送信したエンティティを指します。

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onSignal:<シグナル名>
```

## 例

```yml
# シグナルを送信するモブ
EXAMPLE_MOB:
  Type: CHICKEN
  Skills:
    # 右クリックされたとき、周囲64ブロック内の全MythicMobエンティティに "MOO_FOR_ME" シグナルを送信
    - signal{s=MOO_FOR_ME} @EIR{r=64} ~onInteract
```

```yml
# シグナルを受信するモブ
DUMMY_MOB:
  Type: COW
  Skills:
    # "MOO_FOR_ME" シグナルを受信したとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=MOO} @World ~onSignal:MOO_FOR_ME
```

```yml
# シグナル名を指定しない場合（すべてのシグナルに反応）
DUMMY_MOB:
  Type: COW
  Skills:
    # どんなシグナルを受信してもメッセージを送信
    - message{m="MOO...?"} @World ~onSignal
```

## 実用的な例

```yml
# ボスのフェーズ切り替えシステム
BossPhase1:
  Type: SKELETON
  Display: '&c&lボス フェーズ1'
  Health: 500
  Skills:
    # HP が 50% 以下になったとき、フェーズ2へのシグナルを送信
    - signal{s=PHASE2} @self ~onDamaged ?health{h=<50%}
    # フェーズ2シグナルを受信したとき、フェーズ変更演出
    - message{m="&c&l[!] ボスがフェーズ2に突入！"} @World ~onSignal:PHASE2
    - particle{p=EXPLOSION_HUGE;amount=5} @self ~onSignal:PHASE2
```

## 注意

- シグナル名は英数字のみ使用可能です（スペースや特殊文字は使用不可）。
- シグナル名は大文字・小文字を区別します。

## 関連情報

- [signal メカニック](/Skills/Mechanics/Signal)
- インタラクト時 → [`~onInteract`](onInteract.md)
