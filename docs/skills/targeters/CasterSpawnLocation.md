# @CasterSpawnLocation (キャスタースポーン位置ターゲッター)

## 概要
MythicMobsのキャスターモブのスポーン位置をターゲットにします。

- **タイプ**: 単一場所ターゲッター
- **省略形**: `@casterSpawn`

## 属性
> *このターゲッターには属性がありません*

## 使用例
```yaml
ReturnToSpawn:
  Skills:
  - teleport @CasterSpawnLocation  # キャスターのスポーン地点に戻る
```

## 備考
- MythicMobsとして定義されたモブのスポーン位置を記憶します
- ボスモブが逃げた後に元の位置に戻るパターンに使えます
