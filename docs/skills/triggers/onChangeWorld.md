# onChangeWorld（ワールド変更トリガー）

## 概要

キャスターが別のワールドに移動したときにスキルを実行します。

## エイリアス

- `~onChange_World`
- `~onWorld_Change`
- `~onWorldChange`

## 利用可能なプレースホルダー

| プレースホルダー | 説明 |
|---|---|
| `<skill.var.world>` | 移動先のワールド名（条件分岐に使用可能） |

## 使い方

```yml
モブ名:
  Type: <モブタイプ>
  Skills:
    - <メカニック> ~onChangeWorld
```

## 例

```yml
WorldJumper:
  Type: WITHER_SKELETON
  Skills:
  # ジ・エンドに移動したとき
  - command{c=say The End!} @self ~onChangeWorld ?varEquals{var=skill.world;value=world_the_end}
  # ネザーに移動したとき
  - command{c=say The Nether!} @self ~onChangeWorld ?varEquals{var=skill.world;value=world_nether}
```

```yml
次元旅人:
  Type: ENDERMAN
  Display: '&5次元旅人'
  Health: 100
  Skills:
    # ワールド変更時にアナウンス
    - message{m="&5<self.name> が別のワールドへ移動した！"} @World ~onChangeWorld
    # ネザーに移動したとき
    - potion{t=FIRE_RESISTANCE;d=200;l=1} @self ~onChangeWorld ?varEquals{var=skill.world;value=world_nether}
    # エンドに移動したとき
    - message{m="&5[!] 次元旅人がエンドに現れた！"} @World ~onChangeWorld ?varEquals{var=skill.world;value=world_the_end}
```

## 注意

- `skill.world` プレースホルダーで移動先のワールド名を取得できます。
- ワールド名はサーバーの設定によって異なります（通常 `world`、`world_nether`、`world_the_end`）。

## 関連情報

- テレポート時 → [`~onTeleport`](onTeleport.md)
- スポーン時 → [`~onSpawn`](onSpawn.md)
