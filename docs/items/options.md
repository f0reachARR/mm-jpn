# アイテムオプション (Item Options)

MythicMobsアイテムのOptionsセクションでは、さまざまなアイテム設定を制御できます。

## オプション一覧

### Color（色）

革アーマーや特定のアイテムの色を設定します。RGB値またはカラー名を使用できます。

```yml
example_item:
  Id: leather_chestplate
  Options:
    Color: 255,0,0     # 赤
```

または

```yml
example_item:
  Id: leather_chestplate
  Options:
    Color: RED
```

### AppendType（タイプ追加）

アイテムのツールチップにアイテムタイプを追加するかどうか。

```yml
Options:
  AppendType: true
```

### HideFlags（フラグ非表示）

アイテムのツールチップから特定の情報を非表示にします。

```yml
Options:
  HideFlags: ENCHANTS,ATTRIBUTES
```

### Unbreakable（耐久無限）

アイテムを耐久無限にします。

```yml
Options:
  Unbreakable: true
```

### GlowEffect（光エフェクト）

アイテムにエンチャントの輝きエフェクトを追加します（エンチャントなしで）。

```yml
Options:
  GlowEffect: true
```

### NoWorldDrops（ワールドドロップ無効）

プレイヤーが死亡したときにアイテムがドロップしないようにします。

```yml
Options:
  NoWorldDrops: true
```

### DropOnDeath（死亡時ドロップ）

プレイヤーが死亡したときにアイテムがドロップするかどうか。

```yml
Options:
  DropOnDeath: false
```

## 使用例

```yml
SoulboundSword:
  Id: DIAMOND_SWORD
  Display: '&5魂縛の剣'
  Lore:
  - '&7死んでもなくなることはない剣'
  Options:
    Unbreakable: true
    NoWorldDrops: true
    DropOnDeath: false
    GlowEffect: true
```
