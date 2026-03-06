# Skill（スキル実行）

## 説明

メタスキルを実行します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| skill | s, $, (), m, mechanics, meta, spell | \1の名前 | <!--type:Metaskill--> |
| forcesync | sync | するかどうか | false |
| branch | b, fork, f | Whether the called metaskill's skilltree should branch off from the skilltree of the calling mechanic. The branch will originally clone the skilltree, but any changes made to the branch will not reflect on the original skilltree | false |
| executeafterdeath | continueafterdeath | Whether the metaskill should be able to be called after the caster's death | false |
| snapshotcasterstats | snapshotstats, scs | Whether the caster's stats at the moment of the skill execution should be "saved in memory", so that every subsequent check/fetch operation made against them returns the saved amount. This can be useful if the metaskill includes somewhat big delays and the caster's stats can change during the metaskill execution | false |

## エイリアス

- [x] metaskill
- [x] meta
<!--TAGS-->
<!--tag:Meta-Mechanic-->
