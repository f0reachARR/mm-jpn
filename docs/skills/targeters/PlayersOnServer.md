# @PlayersOnServer (サーバー全体プレイヤーターゲッター)

## 概要
サーバー上のすべてのプレイヤーをターゲットにします。

- **タイプ**: 複数エンティティターゲッター
- **省略形**: `@server`, `@everyone`

## 属性
> *このターゲッターには属性がありません*

## 使用例
```yaml
PlayerCount_ServerWide:
  Skills:
  - setvariable{var=skill.count;val=<skill.targets>} @PlayersOnServer{targetself=true}
  - message{m="サーバー全体に <skill.var.count> 人のプレイヤーがいます"} @self
```

## 備考
- サーバー全体への放送やグローバルイベントに適しています
- すべてのワールドのプレイヤーが対象になります
