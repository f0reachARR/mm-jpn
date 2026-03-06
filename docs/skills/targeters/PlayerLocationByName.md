# @PlayerLocationByName (名前指定プレイヤー位置ターゲッター)

## 概要
名前で指定したプレイヤーの位置をターゲットにします。プレースホルダーを使用できます。

- **タイプ**: 単一場所ターゲッター
- **省略形**: `@specificplayerlocation`

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| name | n | プレイヤーの名前（プレースホルダー使用可） | CarsonJF |

## 使用例
```yaml
ExampleSkill:
  Skills:
  - setblocktype{m=LAVA} @PlayerLocationByName{name=Lxlp}  # 指定プレイヤーの位置にラーバを設置
```

## 備考
- `@PlayerByName` はエンティティをターゲットにしますが、こちらは位置をターゲットにします
- プレイヤーがオフラインの場合は機能しません
