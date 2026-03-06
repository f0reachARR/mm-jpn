# トリガー (Triggers)

トリガーは、モブのスキル設定セクション内でスキルがどのようにトリガーされるかを決定するために使用されます。

**トリガーはメタスキル内で使用できず、含めるべきではありません。**

トリガーはメタスキル自体を*起動する*ためにのみ使用できます（モブの設定ファイル内）。

> 各トリガーは`on`文字列で始まります。その文字列は**大文字小文字を区別する**ため、正しく書かないとトリガーが機能しません。

## トリガーの使用方法

トリガーはモブ設定のSkillsセクションで定義され、前にチルダ(~)を使用する必要があります。タイマーの場合は、ティック単位の時間も必要です。

```yml
SkeletalWizard_Fire:
  Type: WITHER_SKELETON
  Display: '&骸骨の炎の魔法使い'
  Health: 50
  Damage: 0.5
  Skills:
  - ignite{ticks=100} @target ~onAttack
  - skill{s=FireShield} @trigger ~onDamaged 0.1
  - skill{s=AOEFire} ~onTimer:300
```

この例では、モブは近接攻撃時にターゲットに火をつけ、ダメージを受けた際に10%の確率で「FireShield」スキルを使用し、300ティック（15秒）ごとに「AOEFire」スキルを使用します。

## @triggerターゲッター

上の例では[`@trigger`](targeters/trigger.md)ターゲッターが使われています。`@trigger`は、スキルの発動を「引き起こした」エンティティをターゲットにします。例えば、プレイヤーがモブにダメージを与え、そのモブが`~onDamaged`スキルを持つ場合、そのプレイヤーがターゲットになります。

## トリガー一覧

**利用可能なすべてのトリガーの表：**

| トリガー | 発動タイミング |
|---------|--------------|
| [onCombat](triggers/onCombat.md) | デフォルト（戦闘時） |
| [onAttack](triggers/onAttack.md) | モブが何かを攻撃したとき |
| [onDamaged](triggers/onDamaged.md) | モブがダメージを受けたとき |
| [onSpawn](triggers/onSpawn.md) | モブがスポーンしたとき |
| [onDespawn](triggers/onDespawn.md) | モブがデスポーンしたとき |
| [onReady](triggers/onReady.md) | スポナーからモブが初めてスポーンするときにトリガー |
| [onLoad](triggers/onLoad.md) | サーバーリスタート後にモブが読み込まれたとき |
| [onSpawnOrLoad](triggers/onSpawnOrLoad.md) | モブがスポーンまたはロードされたとき |
| [onDeath](triggers/onDeath.md) | モブが死んだとき |
| [onTimer:\#](triggers/onTimer.md) | 指定ティック間隔ごと（#はティック数） |
| [onInteract](triggers/onInteract.md) | モブが右クリックされたとき |
| [onPlayerKill](triggers/onPlayerKill.md) | モブがプレイヤーを倒したとき |
| [onEnterCombat](triggers/onEnterCombat.md) | モブが戦闘に入ったとき（脅威テーブルが必要） |
| [onDropCombat](triggers/onDropCombat.md) | モブが戦闘を離れたとき（脅威テーブルが必要） |
| [onChangeTarget](triggers/onChangeTarget.md) | モブがターゲットを変更したとき（脅威テーブルが必要） |
| [onExplode](triggers/onExplode.md) | モブが爆発したとき（主にクリーパー） |
| [onPrime](triggers/onPrime.md) | クリーパーが爆発のために充電したとき |
| [onCreeperCharge](triggers/onCreeperCharge.md) | クリーパーが帯電したとき（雷がクリーパーに当たったとき） |
| [onTeleport](triggers/onTeleport.md) | モブがテレポートしたとき（主にエンダーマン） |
| [onSignal](triggers/onSignal.md) | モブがシグナルを受信したとき |
| [onShoot](triggers/onShoot.md) | モブが発射物を発射したとき |
| [onBowHit](triggers/onBowHit.md) | モブが発射した発射物がエンティティに当たったとき |
| [onTame](triggers/onTame.md) | モブが手なずけられたとき |
| [onBreed](triggers/onBreed.md) | モブが別のモブと繁殖したとき |
| [onTrade](triggers/onTrade.md) | 村人が取引を完了したとき（Paper必須） |
| [onChangeWorld](triggers/onChangeWorld.md) | モブがワールドを変更したとき |
| [onBucket](triggers/onBucket.md) | 牛が搾乳されたとき、またはエンティティがバケツで捕まえられたとき |
| [onSkillDamage](triggers/onSkillDamage.md) | モブがメカニクスを通じて他のエンティティにダメージを与えたとき |
| [onHear](triggers/onHear.md) | モブが音を聞いたとき（有効化が必要） |
| [onProjectileHit](triggers/onProjectileHit.md) | モブの特殊発射物がエンティティに当たったとき |
| [onProjectileLand](triggers/onProjectileLand.md) | モブの特殊発射物がブロックに当たったとき |
| [onDismounted](triggers/onDismounted.md) | モブが乗り物から降りたとき |
