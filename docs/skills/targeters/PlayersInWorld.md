# @PlayersInWorld (ワールド内全プレイヤーターゲッター)

## 概要
キャスターのワールドにいるすべてのプレイヤーをターゲットにします。

- **タイプ**: 複数エンティティターゲッター
- **省略形**: `@World`

## 属性
> *このターゲッターには属性がありません*

## 使用例
```yaml
PlayerCount:
  Skills:
  - setvariable{var=skill.count;val=<skill.targets>} @PlayersInWorld{targetself=true}
  - message{m="このワールドには <skill.var.count> 人のプレイヤーがいます"} @self
```

## 備考
- ワールドアナウンスやワールド全体への効果に適しています
- `@PlayersOnServer` はサーバー全体を対象にします
