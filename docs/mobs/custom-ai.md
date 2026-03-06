# カスタムAI (Custom AI)

## AIゴールセレクター (AI Goal Selectors)

ゴールセレクターはAIGoalSelectorsフィールドで使用し、モブが何を「したい」かを決定します。特定のカスタムゴールは、作成するモブのベースAIに含まれていない場合は機能しないことがあります。

例:

```yaml
SuperMob:
  Type: zombie
  Health: 200
  Display: 'スーパーゾンビ'
  AIGoalSelectors:
  - clear
  - meleeattack
  - randomstroll
```

このゾンビはプレイヤーを攻撃し、敵をターゲットにしていない時はランダムに歩き回ります。

## 全モブ共通のAIゴール

| AIゴール | エイリアス | 説明 |
|---------|---------|------|
| clear | reset | モブからAIを削除します |
| breakdoors | | モブが走り込んだドアを壊します |
| eatgrass | | モブが時々草を食べます |
| float | swim | モブが水の中を泳ぐようにします |
| lookatplayers | | モブが近くのプレイヤーを見ます |
| LookAtTarget | | モブがターゲットを見ます |
| opendoor | opendoors | モブが走り込んだドアを開け、後ろでドアを閉めます |
| randomlookaround | lookaround | モブがランダムに周りを見回します |
| gotospawnlocation | gotospawn | モブがスポーン位置にパスファインドします |
| doNothing | | 条件が満たされた場合、モブが何もしないようにします（プレミアムのみ） |

## 生物専用のAIゴール

| AIゴール | エイリアス | 説明 |
|---------|---------|------|
| meleeattack | | モブがターゲットに向かって移動し、近接攻撃します |
| movetowardstarget | | モブがターゲットに向かって移動します |
| randomstroll | | モブがランダムに歩き回ります |
| restrictsun | | モブが日光に入るのを防ぎます |
| fleeplayers | runfromplayers | モブがプレイヤーを避けます |
| fleegolems | runfromgolems | モブがアイアンゴーレムを避けます |
| fleevillagers | runfromvillagers | モブが村人を避けます |
| fleewolf | runfromwolves | モブがオオカミを避けます |
| fleefaction | runfromfaction | モブが指定されたファクションのエンティティを避けます |
| fleesun | | 太陽が出ているときにモブが日陰に隠れます |
| fleeConditional | fleeIf | 指定された条件に基づいてモブが逃げます（プレミアムのみ） |
| spiderattack | | スパイダーの攻撃を使います |
| zombieattack | | ゾンビの近接攻撃を使います |
| leapattarget | | モブがターゲットに向かって跳びかかります |
| movethroughvillage | | 村を通り抜けます |
| movetoblock | | モブが特定のタイプのブロックに向かって移動します |
| movetolava | | モブが溶岩に向かって移動します |
| movetowater | | モブが水に向かって移動します |
| movetowardsrestriction | | モブをその「制限ポイント」に向かって移動させます |
| MoveWithinDistanceOfTarget | | 特定の範囲内に収まるようにターゲットに向かって移動します |
| MoveTowardsTargetConditional | | 条件を確認するエンティティへのパスを見つけます（プレミアムのみ） |
| FollowRoute | followpath | モブが特定のパスを1回だけ追跡します |
| patrol x1,y1,z1;x2,y2,z2;... | patrolroute | モブが指定された場所の間をパトロールします |
| gotolocation x,y,z | goto | モブが指定された場所に向かいます |
| gotoowner # | | モブがオーナーから一定の距離を超えたときにオーナーに向かって移動します |
| gotoparent | | モブが親モブに向かって移動します |
| Panic | panicWhenOnFire | 火がついているときにパニックになって走り回り、水を探します |
| randomFly | | ランダムに飛び回ります |
| randomNod | | モブがランダムに頭を縦に振ります |
| horrified | | 激しく走り回ります |

## 動物専用のAIゴール

| AIゴール | エイリアス | 説明 |
|---------|---------|------|
| breed | | モブが他のモブと繁殖できるようにします |

## クリーパー専用のAIゴール

| AIゴール | エイリアス | 説明 |
|---------|---------|------|
| creeperswell | creeperexplode | クリーパーがターゲットに向かって爆発したがります |

## 遠距離エンティティ専用のAIゴール

| AIゴール | エイリアス | 説明 |
|---------|---------|------|
| rangedattack | arrowattack | 基本的な遠距離/発射物攻撃 |
| bowattack | bowshoot, bowmaster | 高度な弓攻撃 |

## ピグリンとピラジャー専用のAIゴール

| AIゴール | エイリアス | 説明 |
|---------|---------|------|
| crossbowAttack | | クロスボウで攻撃します |

---

## AIターゲットセレクター (AI Target Selectors)

ターゲットセレクターはAITargetSelectorsフィールドで使用し、モブがターゲットにしようとするものを決定します。

例:

```yaml
SuperMob:
  Type: zombie
  Health: 200
  AIGoalSelectors:
  - clear
  - meleeattack
  - randomstroll
  AITargetSelectors:
  - clear
  - players
  - golems
```

## 全生物共通のAIターゲット

| AIターゲット | エイリアス | 説明 |
|------------|---------|------|
| clear | | 特別なオプション。モブのすべてのAIをクリアします |
| hurtbytarget | attacker, damager | モブを攻撃したものをターゲットにします |
| monsters | monster | モンスターをターゲットにします |
| Players | player | プレイヤーをターゲットにします |
| Villagers | villager | 村人をターゲットにします |
| irongolem | iron_golem | ゴーレムをターゲットにします |
| nearestConditionalTarget | nearestConditional | 指定された条件を満たす最も近いエンティティをターゲットにします（プレミアムのみ） |
| OwnerAttacker | ownerHurtBy | モブのオーナーを攻撃したものをターゲットにします |
| OwnerTarget | ownerAttack | モブのオーナーが攻撃したものをターゲットにします |
| ParentHurtBy | parentHurtByTarget | モブの親を攻撃したエンティティをターゲットにします |
| ParentTarget | | モブの親がターゲットにしているものをターゲットにします |
| SpecificFaction | | 特定のファクションのエンティティをターゲットにします |
| NearestOtherFaction | | 最も近い別のファクションのエンティティをターゲットにします |
