# ドロップタイプ (Drop Types)

MythicMobsのドロップでは以下のタイプのアイテムや効果を指定できます。

## バニラアイテム

バニラのMinecraftアイテムをドロップさせます。[Material](https://hub.spigotmc.org/javadocs/spigot/org/bukkit/Material.html)の名前を使用します。

```yaml
Drops:
- DIAMOND 1-3 0.5          # 1-3ダイヤモンドを50%の確率で
- ROTTEN_FLESH 1 1.0       # 確実に腐った肉1個
- BONE 1-5 0.8             # 1-5骨を80%の確率で
```

## MythicMobsアイテム

MythicMobsで定義したカスタムアイテムをドロップさせます。

```yaml
Drops:
- DragonSword 1 0.05       # カスタムアイテム「DragonSword」を5%の確率で
- MyHelmet 1 0.1           # カスタムアイテム「MyHelmet」を10%の確率で
```

## 経験値

Minecraft経験値をドロップさせます。

```yaml
Drops:
- exp 100-200 1            # 100-200経験値を確実にドロップ
```

## お金（Money）

Vaultプラグインが必要です。

```yaml
Drops:
- money 100-500 1          # 100-500通貨を確実にドロップ
```

## コマンド（Command）

アイテムをドロップする代わりにコマンドを実行します。

```yaml
Drops:
- cmd{c="give <trigger.name> diamond 1"} 1 0.5
```

コンソールからコマンドを実行する場合：

```yaml
Drops:
- cmd{c="eco give <trigger.name> 1000";ct=CONSOLE} 1 0.8
```

## バニラルートテーブル（VanillaLootTable）

Minecraftのバニラルートテーブルからアイテムをドロップします。

```yaml
Drops:
- vanillaLootTable minecraft:entities/zombie 1 1
```

## 他のドロップシステムとの統合

### MCMMOの経験値

```yaml
Drops:
- mcmmo-exp:mining 500 1   # マイニングスキルに500経験値
- mcmmo-exp:excavation 200 1
```

### Heroesの経験値

```yaml
Drops:
- heroesexp 1000 1
```

### MythicDropsのアイテム

```yaml
Drops:
- mythicdrop SWORD 1 0.5
```

## インラインアイテム

基本的なアイテムをインラインで定義できます：

```yaml
Drops:
- diamond_sword{name="古い剣";lore="さびた剣";enchants=DAMAGE_ALL:1} 1 0.1
- leather_chestplate{color=RED;name="赤い革鎧"} 1 0.5
```

## ドロップテーブルの参照

他のドロップテーブルを参照できます：

```yaml
Drops:
- MyDropTable 1 1          # MyDropTableドロップテーブルを参照
```
