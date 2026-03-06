# AuraRemove（オーラ除去）

## 説明

ターゲットエンティティからオーラを除去します。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| aura | buff, b, a | 除去するオーラの名前 | |

## 使用例

```yaml
  Skills:
  - auraremove{aura=MyBuff} @self ~onTimer:100
```

## エイリアス
- [x] removebuff
- [x] removethreat
- [x] removedot
- [x] removeaura
