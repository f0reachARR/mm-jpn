# @ThreatTable (脅威テーブルターゲッター)

## 概要
キャスターモブの脅威テーブル（Threat Table）上のすべてのエンティティをターゲットにします。

- **タイプ**: 複数エンティティターゲッター（脅威テーブル）
- **省略形**: `@TT`, `@threattargets`

## 属性
> *このターゲッターには属性がありません*

## 使用例
```yaml
ExampleSkill:
  Skills:
  - ignite @ThreatTable  # 脅威テーブル上のすべてのエンティティに火をつける
```

## 備考
- **脅威テーブル（ThreatTable）機能が有効なモブのみで機能します**
- 脅威テーブルは戦闘中に攻撃や治癒などの行動によって変動します
- 脅威テーブルの設定については [ThreatTables](/Mobs/ThreatTables) を参照してください
