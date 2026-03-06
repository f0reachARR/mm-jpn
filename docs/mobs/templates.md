# テンプレート (Templates)

テンプレートを使用すると、複数のモブやアイテムで共通の設定を共有できます。これにより設定の重複を避け、メンテナンスを容易にします。

## 基本的な使用方法

```yaml
MyMob:
  Template: BaseTemplate
  Type: ZOMBIE
  # BaseTemplateの設定が引き継がれます
```

```yaml
BaseTemplate:
  Health: 100
  Damage: 10
  Options:
    MovementSpeed: 0.2
    PreventOtherDrops: true
```

## 複数のテンプレート

複数のテンプレートを使用でき、テンプレートはカンマで区切ります：

```yaml
MyMob:
  Template: Template1, Template2
```

## テンプレートのネスト

テンプレートはそれ自体でテンプレートを使用できます：

```yaml
AdvancedTemplate:
  Template: BaseTemplate
  Health: 200
```

## 注意事項

- テンプレートに設定された値はデフォルト値として機能します
- モブに直接設定された値はテンプレートの値を上書きします
- テンプレートにはTypeを含まないことが一般的ですが、含めることもできます

## 例

```yaml
# テンプレート
BossBase:
  Health: 500
  Options:
    AlwaysShowName: true
    PreventOtherDrops: true
    MovementSpeed: 0.25
  BossBar:
    Enabled: true
    Range: 50
    Color: RED

# このテンプレートを使用するモブ
SkeletonBoss:
  Template: BossBase
  Type: WITHER_SKELETON
  Display: '&6スケルトンボス'
  BossBar:
    Title: 'スケルトンボス'
    Color: PURPLE  # テンプレートのREDをオーバーライド

ZombieBoss:
  Template: BossBase
  Type: ZOMBIE
  Display: '&cゾンビボス'
  Health: 800  # テンプレートの500をオーバーライド
  BossBar:
    Title: 'ゾンビボス'
```
