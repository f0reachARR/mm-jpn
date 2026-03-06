# onCombat（戦闘トリガー）

## 概要

トリガーを指定しない場合のデフォルトトリガーです。  
以下のイベントが発生したときにスキルを実行します：

- モブがダメージを与えたとき
- モブがダメージを受けたとき
- モブがスポーンしたとき
- モブが死亡したとき

> **注意：** `~onCombat` は広範なイベントをカバーするため、より特定のトリガー（`~onAttack`、`~onDamaged` など）の使用を推奨します。

## 使い方

スキルのトリガーとしてそのまま `~onCombat` を指定するか、トリガーを省略することでデフォルトで適用されます。

## 例

```yml
SkeletalWarrior:
  Mobtype: skeleton
  Display: '<blue>A Skeletal Warrior</blue>'
  Skills:
  - skill{s=Bash} =10%-90%
```

上記の例ではトリガーを明示していませんが、`~onCombat` がデフォルトとして適用されます。

```yml
戦闘モブ例:
  Type: ZOMBIE
  Display: '&c戦闘ゾンビ'
  Health: 100
  Skills:
    # 戦闘イベント（ダメージ・スポーン・死亡）のたびにメッセージを表示
    - message{m="戦闘トリガー発動！"} @World ~onCombat
```

## 関連情報

- より具体的な状況には専用のトリガーを使用してください：
  - ダメージを与えたとき → [`~onAttack`](onAttack.md)
  - ダメージを受けたとき → [`~onDamaged`](onDamaged.md)
  - スポーン時 → [`~onSpawn`](onSpawn.md)
  - 死亡時 → [`~onDeath`](onDeath.md)
