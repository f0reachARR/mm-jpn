# onSkillDamage（スキルダメージトリガー）

## 概要

モブがメカニック（スキル）を通じて他のエンティティにダメージを与えたときにスキルを実行します。  
通常の近接攻撃や矢によるダメージには発火しません。`damage` メカニックなどのスキルによるダメージが対象です。

> **[@trigger](/Skills/Targeters/Trigger) ターゲター**はダメージを受けたエンティティを指します。

## エイリアス

- `~onSkillHit`
- `~onSkill_Damage`

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onSkillDamage
```

## 例

```yml
ExampleMob:
  Type: 
  Skills:
  # 20ティックごとに周囲10ブロック内にダメージを与える
  - damage @PIR{r=10} ~onTimer:20
  # スキルダメージが発生したとき、ダメージを受けたエンティティにメッセージ
  - message{m="Get damaged! MUHAHAHA"} @trigger ~onSkillDamage
```

```yml
魔法使いモブ:
  Type: WITCH
  Display: '&5魔法使い'
  Health: 150
  Skills:
    # 5秒ごとに周囲8ブロック内の全エンティティに呪文ダメージを与える
    - damage{a=15} @PIR{r=8} ~onTimer:100
    # スキルダメージを与えたとき、ダメージを受けたエンティティを鈍化させる
    - potion{t=SLOW;d=60;l=2} @trigger ~onSkillDamage
    # スキルダメージを与えたとき、エフェクトを表示
    - particle{p=WITCH;amount=10;hs=0.3;vs=0.3} @trigger ~onSkillDamage
    # スキルダメージを与えたとき、魔法使いのHPを少し回復（吸血効果）
    - heal{a=5} @self ~onSkillDamage
```

## 注意

- このトリガーは `damage` メカニックや他のダメージ系メカニックによるダメージに反応します。
- 通常の近接攻撃（`~onAttack`）や弓矢（`~onBowHit`）には反応しません。

## 関連情報

- 通常攻撃時 → [`~onAttack`](onAttack.md)
- 弓矢命中時 → [`~onBowHit`](onBowHit.md)
- 特殊飛び道具命中時 → [`~onProjectileHit`](onProjectileHit.md)
