# ShootFireball（火球射出）

## 説明

火球を射出します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| yield | strength, y, s | \1の名前 | 1 |
| velocity | v | 最大初期速度 | 1 |
| fireTicks | ft | How long (in ticks) fire left behind by the fireball will persist | 0 |
| incendiary | i | (true/false) Whether the fireball will leave behind fire | false |
| charged | c | Whether the fireball is charged | false |
| fromorigin | fo | Whether the fireball should be shot from the [origin] | false |
| playsound | ps | するかどうか | false |
| smallfireball | small,sml | するかどうか | false |
| type | t | \1の名前 | SMALL<!--type:ShootFireball_Type--> |
| item | material | The [material] of the fireball, if ITEM type was used | BLAZE_POWDER<!--type:Material--> |

## エイリアス

- [x] fireball
<!-- LINKS -->
[origin]: /Skills/Targeters/Origin
[material]: https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html
<!--TAGS-->
<!--tag:Projectile-->
