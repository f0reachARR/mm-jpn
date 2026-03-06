# ItemSpray（アイテム噴射）

## 説明

ターゲット位置に一時的なアイテムを噴射します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| items | item, i | \1の名前 | iron_sword<!--type:Item--> |
| amount | a | How many items will render from the spray | 10 |
| duration | d | How long (in ticks) the items will exist | 20 |
| radius | r | ターゲット周囲の半径 | 0 |
| velocity | v, force, f | 最大初期速度 | 1 |
| yVelocity | yv, yforce, yf | \1の名前 | `velocity` |
| yOffset | yo, y | \1の名前 | 1 |
| allowpickup | ap | Whether the itemspray's items should be real items, enabling players to pick them up | false |
| gravity | g | Whether the items should be affected by gravity | true |
| audience |  | メッセージの[オーディエンス] | world<!--type:Audience--> |

## エイリアス

- [x] effect:itemspray
- [x] e:itemspray
<!-- LINKS -->
[Bukkit]: https://hub.spigotmc.org/javadocs/bukkit/org/bukkit/Material.html
[audience]: /Skills/Audience
<!--TAGS-->
<!--tag:Effect-->
<!--tag:Item-->
