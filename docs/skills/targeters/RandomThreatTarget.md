# @RandomThreatTarget (ランダム脅威ターゲット)

## 概要
キャスターモブの脅威テーブルからランダムに1つのエンティティをターゲットにします。

- **タイプ**: 単一エンティティターゲッター（脅威テーブル）
- **省略形**: `@RTT`, `@threattablerandomtarget`

## 属性
> *このターゲッターには属性がありません*

## 使用例
```yaml
ExampleSkill:
  Skills:
  - ignite @RandomThreatTarget  # 脅威テーブルからランダムに選んだエンティティに火をつける
```

## 備考
- **脅威テーブル（ThreatTable）機能が有効なモブのみで機能します**
- 脅威値に関係なくランダムに選択します
- 脅威テーブルの設定については [ThreatTables](/Mobs/ThreatTables) を参照してください
