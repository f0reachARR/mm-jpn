# Summon（召喚）

## 説明

ターゲット位置にモブを召喚します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| type | t, mob, m | 召喚するモブのタイプ | SKELETON<!--type:Mob--> |
| onSummon | onsummonskill, then | 召喚されたモブに実行する[メタスキル] | <!--type:Metaskill--> |
| amount | a | 召喚するモブの数 | 1 |
| level | l | モブのレベル | 0 |
| yaw |  | 召喚されたエンティティのヨー |  |
| pitch |  | 召喚されたエンティティのピッチ |  |
| usetargetyaw | uty | ターゲットのヨーを召喚エンティティのヨーに使用するか | false |
| usetargetpitch | utp | ターゲットのピッチを召喚エンティティのピッチに使用するか | false |
| radius | r, noise, n | ターゲット周囲の半径 | 0 |
| yRadius | yr, ynoise, yn | radius のY成分を上書き | radius |
| yRadiusUpOnly | yradiusonlyup, yruo, yu | Yの広がりを上方向のみにするか | false |
| velocity | v, force, f | 最大初期速度 | 0 |
| yvelocity | yv, yforce, yf | Same as velocity, but only applied to the y axis | velocity |
| onSurface | os, s | (true/false) Whether the mobs should be spawned only on a solid block | false |
| copyThreatTable | ctt | 召喚されたモブが親のスレットテーブルをコピーするか | false |
| inheritThreatTable | itt | 召喚されたモブが親のスレットテーブルを共有するか | false |
| inheritFaction | if | 召喚されたモブが親と同じ派閥を持つか | true |
| inheritdespawn | inheritdespawnoption, ido | 召喚されたモブがキャスターのデスポーンオプションを継承するか | false |
| summonerIsOwner | sio | 召喚者をオーナーとして設定するか | true |
| summonerIsParent | sip | 召喚者を親として設定するか | true |

## エイリアス

- [x] spawnmobs
- [x] spawnmob
- [x] piratesummon
<!-- LINKS -->
[metaskill]: /Skills/Metaskills
<!--TAGS-->
<!--tag:Summon-->
<!--tag:Meta-Mechanic:Thenable-->
