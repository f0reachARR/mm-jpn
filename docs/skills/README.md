# スキル (Skills)

スキルはMythicMobsの重要な機能です。
すべてのモブ（[Crucible](https://git.mythiccraft.io/mythiccraft/mythiccrucible)アドオンをお持ちの場合はアイテムも）は、異なる状況でさまざまな条件で発動できるさまざまなタイプのスキルを持つことができます。MythicMobのスキルシステムは、慣れれば非常に直感的で、シンプルなモブから非常に複雑なボスまで何でも作成できます。

スキルはいくつかの異なる部分で構成されています：

- [メカニクス (Mechanics)](mechanics.md)
- [ターゲッター (Targeters)](targeters.md)
- [トリガー (Triggers)](triggers.md)
- [コンディション (Conditions)](conditions.md)

## はじめに

スキルとは何でしょうか？

スキルは[スキルメカニクス](mechanics.md)、または「ベーススキル」で構成されています。これらはMythicMobsに付属するシンプルな基本スキルです。各スキルメカニクスはモブの**Skills**セクションで呼び出されます。例を見てみましょう：

```yaml
FieryZombie:
  Type: ZOMBIE
  Display: '炎のゾンビ'
  Health: 50
  Skills:
  - mechanic1
  - skill{skill=Skill1}
  - skill{s=Skill2}
  - skill:Skill3
```

各スキルメカニクスは上記のようなリスト形式でモブに割り当てられます。実際のメカニクスはどのようなものでしょうか？実際の例を示します：

```yaml
FieryZombie:
  Type: ZOMBIE
  Display: '炎のゾンビ'
  Health: 50
  Skills:
  - ignite{ticks=100} @target ~onAttack <50% 0.5
```

各部分を分解してみましょう：

```yaml
Skills:
- mechanic{argument=value} @[targeter] ~on[trigger] [health_modifier] [chance]
```

## メカニクス（Mechanics）

スキルの最初で最も重要な部分は、メカニクスです。これは実行したいことです。ダメージを与えたり、何かに火を付けたり、雷を落としたりすることです。[多くの異なるメカニクス](mechanics.md)を使用できますが、主に2つのタイプがあります：エンティティをターゲットにするメカニクスと、場所をターゲットにするメカニクスです。

多くのメカニクスには引数があります。これらはメカニクス名の直後に来て、中括弧{}で囲まれています。各引数はセミコロン(;)で区切られます。

```yaml
Skills:
- mechanic{option1=value;option2=value}
```

例えば、誰かを5秒間燃やしたい場合は、igniteメカニクスを使用して"ticks"オプションを100に設定します（1秒に20ティックあります）：

```yaml
Skills:
- ignite{ticks=100}
```

## ターゲッター（Targeters）

ターゲッターはスキルの実装の別のコア部分です。ターゲッターは「スキルの対象となるもの」です。多くのタイプのターゲッターがあり、ほとんどは「エンティティ」または「場所」をターゲットにすることで分類できます。

ターゲッターはスキルラインのメカニクスの直後に来て、常に@記号でプレフィックスされます。

```yaml
Skills:
- mechanic{option=value} @targeter{option1=value;option2=value}
```

例えば、モブのターゲットを燃やしたい場合：

```yaml
Skills:
- ignite{ticks=100} @target
```

または、近くの全プレイヤーを燃やしたい場合（5ブロック範囲内）：

```yaml
Skills:
- ignite{ticks=100} @PlayersInRadius{radius=5}
```

## トリガー（Triggers）

トリガーはスキルの非常に重要な部分です。トリガーは「このスキルが発生する原因となるもの」を決定します。

トリガーはターゲッターの直後に来て、一般的に **~on** で始まり、その後にトリガー名が続きます。

```yaml
Skills:
- mechanic{option=value} @targeter{option=value} ~onTrigger
```

例えば、モブが攻撃するとき（近接攻撃が火も適用するように）にトリガーを発動させたい場合：

```yaml
Skills:
- ignite{ticks=100} @target ~onAttack
```

## HP修飾子（Health Modifiers）

HP修飾子は、スキルを実行するHP範囲を簡単に設定できる特別なタイプの条件です。いくつかのシンプルな形式があります：

- **=90%** - モブのHPが90%未満のときのみスキルが発動します。（1回だけ発動します）
- **<50%** - モブのHPが50%未満のときのみスキルが発動します。
- **=30%-50%** - モブのHPが30%から50%の間のときのみスキルが発動します。
- **<2000** - モブのHPが2000未満のときのみスキルが発動します。
- **>500** - モブのHPが500を超えるときのみスキルが発動します。

```yaml
Skills:
- mechanic{option=value} @targeter{options=value} ~onTrigger <50%
```

## 確率（Chance）

確率は別のシンプルなオプション条件です。確率は常にスキルラインの最後に来て、1.0が100%、0.5が50%、0が0%のシンプルな小数です。

```yaml
Skills:
- ignite{ticks=100} @target ~onAttack <50% 0.5
```

## まとめ

個別のベーススキルを使いこなせたら、メタスキルを使ってそれらをより複雑なスキルに組み合わせることができます。

## チートシート

![スキルシート](https://git.lumine.io/mythiccraft/MythicMobs/uploads/ebf67740e7bc604db56a95cf62397030/image.png)

## サブページ

- [メカニクス](mechanics.md)
- [ターゲッター](targeters.md)
- [トリガー](triggers.md)
- [コンディション](conditions.md)
- [メタスキル](meta-skills.md)
- [変数](variables.md)
- [プレースホルダー](placeholders.md)
- [スキルコマンド](skill-commands.md)
- [上級ユーザーガイドとテクニック](advanced-techniques.md)
