# キルメッセージ (Kill Messages)

KillMessages機能を使用すると、モブがプレイヤーを倒したときに表示されるデスメッセージをカスタマイズできます。

## 基本的な使用方法

```yaml
example_mob:
  Type: zombie
  Display: タンカー
  KillMessages:
  - <caster.name>が<target.name>をぶっ飛ばした！
  - お前は弱すぎる、<target.name>！
```

複数のメッセージが設定されている場合、ランダムに1つが選択されます。

## プレースホルダー

KillMessagesでは以下のプレースホルダーが使用できます：

- `<caster.name>` - モブの名前
- `<target.name>` - 倒されたプレイヤーの名前
- `<target.l.x>`, `<target.l.y>`, `<target.l.z>` - 倒された場所の座標

## カラーコード

キルメッセージにはカラーコードを使用できます：

```yaml
KillMessages:
- '&c<target.name>&rは&6<caster.name>&rに倒されました！'
- '&7<target.name>&rが世界を去った... &6<caster.name>&rによって。'
```

## 例

```yaml
DragonBoss:
  Type: WITHER_SKELETON
  Display: '&5ドラゴンの主'
  KillMessages:
  - '&5ドラゴンの主&rが&c<target.name>&rを倒した！'
  - '&c<target.name>&rはドラゴンの炎に焼かれた！'
  - '&c<target.name>&rよ、貴様は弱すぎる！'
```
