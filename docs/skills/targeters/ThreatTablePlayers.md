# @ThreatTablePlayers (脅威テーブルプレイヤーターゲッター)

## 概要
キャスターモブの脅威テーブル上のすべてのプレイヤーをターゲットにします。

- **タイプ**: 複数エンティティターゲッター（脅威テーブル）
- **省略形**: `@ttp`, `@playersinthreattable`

## 属性
> *このターゲッターには属性がありません*

## 使用例
```yaml
ExampleSkill:
  Skills:
  - ignite @ThreatTablePlayers  # 脅威テーブル上のすべてのプレイヤーに火をつける
```

## 備考
- **脅威テーブル（ThreatTable）機能が有効なモブのみで機能します**
- `@ThreatTable` はエンティティ全体、こちらはプレイヤーのみを対象にします
- 脅威テーブルの設定については [ThreatTables](/Mobs/ThreatTables) を参照してください
