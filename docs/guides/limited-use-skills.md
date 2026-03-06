# ガイド: 制限付き使用スキル

このガイドでは、モブがスキルを使用できる回数を制限する方法を説明します。

## 変数を使った制限

変数システムを使ってスキルの使用回数を追跡します：

```yaml
LimitedSkillMob:
  Type: ZOMBIE
  Display: '&6限定スキルモブ'
  Health: 500
  Variables:
    specialSkillUses: int/0   # スポーン時に変数を0に設定
  Skills:
  - skill{s=LimitedSpecialSkill} ~onTimer:100
```

```yaml
LimitedSpecialSkill:
  Conditions:
  - variablelookup{var=caster.specialSkillUses;v=<3} true  # 3回未満のときのみ
  Skills:
  - variableadd{var=caster.specialSkillUses;amount=1}  # カウンターを増加
  - message{m="&6特別攻撃！（<caster.var.specialSkillUses>/3回目）"} @PlayersInRadius{r=20}
  - effect:particles{p=FLAME;amount=50} @PlayersInRadius{r=5}
  - damage{amount=25} @PlayersInRadius{r=5}
```

## タグを使った制限（1回のみ）

スコアボードタグを使って一度だけ使えるスキルを作成します：

```yaml
OneTimeSkillMob:
  Type: ZOMBIE
  Display: '&5一撃必殺モブ'
  Health: 1000
  Skills:
  - skill{s=OneTimeUltimate} =50%  # HPが50%になったとき
```

```yaml
OneTimeUltimate:
  Conditions:
  - hastag{tag=usedUltimate} false  # タグがない場合のみ
  Skills:
  - settag{tag=usedUltimate} @self  # タグを設定して再使用を防止
  - message{m="&5究極の一撃！！！"} @PlayersInRadius{r=50}
  - effect:particles{p=EXPLOSION_LARGE;amount=10;radius=10} @self
  - damage{amount=100;ignorearmor=true} @PlayersInRadius{r=8}
  - throw{velocity=20;velocityY=10} @PlayersInRadius{r=8}
```

## クールダウンを使った制限

メタスキルのCooldownオプションを使用します：

```yaml
CooldownSkillMob:
  Type: ZOMBIE
  Skills:
  - skill{s=CooldownedSkill} ~onTimer:20

CooldownedSkill:
  Cooldown: 30  # 30秒に一度だけ使用可能
  Skills:
  - message{m="クールダウン付きスキルが発動！"} @PlayersInRadius{r=20}
  - damage{amount=20} @PlayersInRadius{r=5}
```
