# @Location (座標指定ターゲッター)

## 概要
ワールド内の指定した座標をターゲットにします。

- **タイプ**: 単一場所ターゲッター
- **省略形**: `@l`, `@loc`

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| location | loc, l, c | `x,y,z,yaw,pitch` 形式のフル座標 | |
| x | | `location` が未設定の場合のX座標 | 0 |
| y | | `location` が未設定の場合のY座標 | 0 |
| z | | `location` が未設定の場合のZ座標 | 0 |
| yaw | | `location` が未設定の場合のYaw | 0 |
| pitch | | `location` が未設定の場合のPitch | 0 |
| world | w | ターゲットするワールド（未設定の場合はキャスターのワールド） | |

## 使用例
```yaml
ExampleSkill:
  Skills:
  - setblock{m=DIAMOND_BLOCK} @Location{location=100,70,-120,0,0}   # フル座標で指定
  - setblock{m=EMERALD_BLOCK} @Location{x=100;y=71;z=-120}           # 個別座標で指定
```

## 備考
- 固定された世界座標をターゲットにする場合に使用します
- プレースホルダーを使って動的な座標を指定することもできます
