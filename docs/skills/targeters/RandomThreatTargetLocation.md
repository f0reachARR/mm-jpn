# @RandomThreatTargetLocation (ランダム脅威ターゲット位置)

## 概要
キャスターモブの脅威テーブルからランダムに選んだエンティティの位置をターゲットにします。

- **タイプ**: 単一場所ターゲッター（脅威テーブル）
- **省略形**: `@RTTL`

## 属性
> *このターゲッターには属性がありません*

## 使用例
```yaml
ExampleSkill:
  Skills:
  - effect:particles{y=2} @RandomThreatTargetLocation  # ランダムな脅威ターゲットの位置にパーティクルを表示
```

## 備考
- **脅威テーブル（ThreatTable）機能が有効なモブのみで機能します**
- エンティティではなく「場所」をターゲットにします
- 脅威テーブルの設定については [ThreatTables](/Mobs/ThreatTables) を参照してください
