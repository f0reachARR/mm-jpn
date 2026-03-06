# onDropCombat（戦闘離脱トリガー）

## 概要

モブが戦闘状態から抜けたときにスキルを実行します。

> **⚠️ [ThreatTables（脅威テーブル）](/Mobs/ThreatTables) の有効化が必要です。**

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**は関連しません。

## エイリアス

- `~onLeaveCombat`
- `~onCombatDrop`
- `~onExitCombat`

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Modules:
    ThreatTable: true
  Skills:
    - <メカニック> ~onDropCombat
```

## 例

```yml
EXAMPLE_MOB:
  Type: CHICKEN
  Modules:
    ThreatTable: true
  Skills:
    # モブが戦闘状態を離脱したとき、ワールド全体のプレイヤーにメッセージを送信
    - message{m=DROPPED COMBAT} @World ~onDropCombat
```

```yml
戦闘リセットモブ:
  Type: SKELETON
  Display: '&7ガードスケルトン'
  Health: 200
  Modules:
    ThreatTable: true
  Skills:
    # 戦闘離脱時にHPを全回復
    - sethealth{h=200} @self ~onDropCombat
    # 戦闘離脱時にバフを解除
    - removePotions @self ~onDropCombat
    # 戦闘離脱時にメッセージ
    - speak{m="&7...また来い。"} ~onDropCombat
```

## 注意

- このトリガーは ThreatTable を有効にしないと機能しません。
- 戦闘離脱条件はThreatTableの設定に依存します（デフォルトでは一定時間ターゲットが脅威を与えなくなった場合）。

## 関連情報

- 戦闘開始時 → [`~onEnterCombat`](onEnterCombat.md)
- ターゲット変更時 → [`~onChangeTarget`](onChangeTarget.md)
- [ThreatTables の設定](/Mobs/ThreatTables)
