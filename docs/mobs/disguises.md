# ディスガイズ (Disguises)

ディスガイズ機能を使用すると、モブの外観を他のエンティティタイプのように変更できます。これには[LibsDisguises](https://www.spigotmc.org/resources/libs-disguises-free.81/)プラグインが必要です。

## 前提条件

- サーバーに[LibsDisguises](https://www.spigotmc.org/resources/libs-disguises-free.81/)がインストールされ機能していること

## 基本的な使用方法

```yaml
# このモブはゾンビとして動作しますが、チキンのように見えます
example_mob:
  Type: zombie
  Disguise: chicken
```

## 高度な使用方法

特定のディスガイズオプションを設定できます：

```yaml
example_mob:
  Type: zombie
  Disguise: player <PlayerName> setDisguiseName <DisplayName>
```

## プレイヤーディスガイズ

プレイヤーに変装するには：

```yaml
example_mob:
  Type: zombie
  Display: '&6プレイヤーのように見えるゾンビ'
  Disguise: player Steve setDisguiseName &6怪しいプレイヤー
```

> プレイヤーディスガイズでカラーコードを使用するには、Disguise:オプションを使用し、カラーコードを一重引用符(' ')で囲んでください。

## インタラクティブディスガイズ

[Disguise](../skills/mechanics/disguise.md)メカニクスを使用して、スキルでモブのディスガイズを動的に変更できます。

## 注意事項

- ディスガイズはモブの外観のみを変更し、動作には影響しません
- パッシブモブタイプのディスガイズでも、AIはベースのモブタイプに基づきます
- ディスガイズはサーバーのパフォーマンスに影響する場合があります
