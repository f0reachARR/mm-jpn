# Raytrace（レイトレース）

## 説明

ターゲットまで直線をトレースします。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| entityskill | eskill, es | meta-skill to use when the ray hits an entity | <!--type:Metaskill--> |
| locationskill | lskill, ls | meta-skill to use when the ray hits a location | <!--type:Metaskill--> |
| headshotskill | hsskill, hs | meta-skill to use when it's a headshot | <!--type:Metaskill--> |
| maxdistance | distance, md, d | max distance to trace | 50 |
| raywidth | rw, w | Width of the ray traced | 0.2 |
| ignoreentities | ignoreentity, ie | Whether entities should be ignored, so that the raytrace will never be stopped by them | false |
| ignorepassableblocks | ignorepassable, ip | ignores collision of passable blocks | true |
| fluidcollisionmode | fcm | [Determines the collision behaviour when fluids get hit during ray tracing](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/FluidCollisionMode.html) | NEVER<!--type:FluidCollisionMode--> |
| accuracy | ac, a | spread of the traced ray | 1 |
| verticalnoise | vn | vertical spread of the ray | 0 |
| horizontalnoise | hn | horizontal spread of the ray | 0 |
| raytraceConditions | rc, rcond, rconditions | Conditions applied to the raytraced target | <!--type:Conditions--> |
| headshotmultiplier | hsmultipler, hsm | headshot power multiplier | 1 |
