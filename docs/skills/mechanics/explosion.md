# Explosion（爆発）

## 説明

爆発を引き起こします。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| power | p | 爆発の強度 | 3 |
| fire | f | 爆発後に炎を残すか | false |
| breakblocks | bb, b | ブロックを破壊するか | false |

## 使用例

```yaml
  Skills:
  - explosion{power=5;fire=true;breakblocks=true} @target ~onTimer:20
```

## エイリアス
- [x] e
- [x] explode
