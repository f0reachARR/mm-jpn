# RaytraceTo（指定位置レイトレース）

## 説明

ターゲット位置へのレイトレースの結果でスキルを実行します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| startyoffset | syo, ystartoffset, ys | \1の名前 | 0 |
| targetyoffset | tyo, ytargetoffset, yt | \1の名前 | 0 |
| fromorigin | fo | If they ray should start from the origin of the mechanic | false |
| useeyelocation | uel | If they ray should start from the eye location of the caster | false |
| forwardoffset | startfoffset, sfo | \1の名前 | 0 |
| sideoffset | soffset, sso | \1の名前 | 0 |
| entityskill | eskill, es | meta-skill to use when the ray hits an entity | <!--type:Metaskill--> |
| locationskill | lskill, ls | meta-skill to use when the ray hits a location | <!--type:Metaskill--> |
| headshotskill | hsskill, hs | meta-skill to use when it's a headshot | <!--type:Metaskill--> |
| maxdistance | distance, md, d | max distance to trace | 50 |
| raywidth | rw, w | Width of the ray traced | 0.2 |
| ignorepassableblocks | ignorepassable, ip | ignores collision of passable blocks | true |
| ignoreentities | ignoreentity, ie | ignores all entities | false |
| fluidcollisionmode | fcm | [Determines the collision behaviour when fluids get hit during ray tracing](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/FluidCollisionMode.html) | NEVER<!--type:FluidCollisionMode--> |
| accuracy | ac, a | spread of the traced ray | 1 |
| verticalnoise | vn | vertical spread of the ray | 0 |
| horizontalnoise | hn | horizontal spread of the ray | 0 |
| raytraceConditions | rc, rcond, rconditions | Conditions applied to the raytraced target | <!--type:Conditions--> |
| headshotmultiplier | hsmultipler, hsm | headshot power multiplier | 1 |
