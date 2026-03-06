# ガイド: NPCの作成

このガイドでは、MythicMobsを使って動かない静的なNPCを作成する方法を説明します。

## 前提条件

NPCを作成するには、MythicMobsのみが必要です。より高度なNPCを作成したい場合はLibsDisguisesがあると良いでしょう。

## 基本的なNPC

```yaml
SimpleNPC:
  Type: ZOMBIE
  Display: '&e商人ジョン'
  Health: 9999
  Damage: 0
  Options:
    AlwaysShowName: true
    Despawn: PERSISTENT
    NoAI: false
    MovementSpeed: 0
    Invincible: true
    PreventOtherDrops: true
    Silent: true
  AIGoalSelectors:
  - clear
  - lookatplayers
  - randomlookaround
  AITargetSelectors:
  - clear
  Disguise: player Steve  # LibsDisguisesが必要
```

## インタラクティブNPC

プレイヤーがNPCを右クリックしたときにセリフを言うNPCを作成できます：

```yaml
TalkingNPC:
  Type: ZOMBIE
  Display: '&e衛兵隊長'
  Health: 9999
  Damage: 0
  Options:
    AlwaysShowName: true
    Despawn: PERSISTENT
    Invincible: true
    PreventOtherDrops: true
    Silent: true
  AIGoalSelectors:
  - clear
  - lookatplayers
  AITargetSelectors:
  - clear
  Skills:
  - skill{s=GuardDialogue} @trigger ~onInteract
  Disguise: player Guard

# スキルファイル
GuardDialogue:
  Cooldown: 5
  Skills:
  - message{m="&e衛兵隊長<&co> &f街への入場を許可します。行ってください。"} @trigger
```

## コマンド実行NPC

プレイヤーがNPCをクリックしたときにコマンドを実行するNPCを作成できます：

```yaml
ShopNPC:
  Type: ZOMBIE
  Display: '&6道具屋'
  Health: 9999
  Options:
    Despawn: PERSISTENT
    Invincible: true
    PreventOtherDrops: true
    Silent: true
  AIGoalSelectors:
  - clear
  - lookatplayers
  AITargetSelectors:
  - clear
  Skills:
  - skill{s=OpenShop} @trigger ~onInteract

# スキルファイル
OpenShop:
  Cooldown: 1
  Skills:
  - command{c="shop open toolshop <trigger.name>";ct=CONSOLE} @trigger
```

## NPCをスポナーで固定する

NPCを特定の場所に固定するにはスポナーを使用します：

```
/mm spawners create ShopNPCSpawner ShopNPC
/mm s set ShopNPCSpawner leashrange 0
/mm s set ShopNPCSpawner maxmobs 1
/mm s set ShopNPCSpawner cooldown 30
```

これにより、NPCが移動しないように固定され、削除されても再スポーンします。
