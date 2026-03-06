# インラインコンディション (Inline Conditions)

インラインコンディションは、より基本的なことのためにメタスキル全体を作成することなく、個々のメカニクスやターゲッターに対してコンディションを使用できます。

## コンディション（キャスターのチェック）

これらのコンディションはキャスター自体に対してチェックします。メカニクス行の最後に`?`で始まります。

```yaml
SkeletalKnight:
  Type: WITHER_SKELETON
  Skills:
  - message{m="雨の中で攻撃するとは！"} @trigger ~onDamaged ?raining
```

コンディションをtrueにするには`?`を、falseにするには`?!`を使います：
- `?raining` - 雨が降っている場合にtrue
- `?!raining` - 雨が降っていない場合にtrue

## トリガーコンディション

トリガーに対してチェックするには、`?`の後に`~`を使います：

```yaml
SkeletalKnight:
  Type: WITHER_SKELETON
  Skills:
  - message{m="木の剣で攻撃するとは？"} @trigger ~onDamaged ?~holding{m=WOODEN_SWORD}
```

- `?~holding{m=WOODEN_SWORD}` - プレイヤーが木の剣を持っている場合にtrue
- `?~!holding{m=WOODEN_SWORD}` - プレイヤーが木の剣を持っていない場合にtrue

### 複数のコンディション

必要なだけインラインコンディションを使用できます。**すべての**コンディションを満たす必要があります：

```yaml
SkeletalKnight:
  Type: WITHER_SKELETON
  Skills:
  - message{m="夜の雨の中、木の剣で！"} @trigger ~onDamaged ?raining ?night ?~holding{m=WOODEN_SWORD}
```

## ターゲットコンディション（プレミアム限定）

インラインターゲットコンディションはターゲッターに適用でき、特定のエンティティや場所のみをターゲットにします。

書式：

```yaml
SkeletalKnight:
  Type: WITHER_SKELETON
  Skills:
  - damage{a=1} @PIR{r=10;conditions=[  - hasaura{aura=Plagued} true ]} ~onTimer:20
```

> **重要**: スペースの配置が重要です：
> - `conditions=[` と最初のコンディションの間に**2スペース**
> - 最後のコンディションの`true`/`false`の後に**1スペース**

### 複数のターゲットコンディション

行を分けた書き方：

```yaml
SkeletalKnight:
  Type: WITHER_SKELETON
  Skills:
  - damage{a=1} @PIR{r=10;conditions=[
                            - hasaura{aura=Plagued} false
                            - haspotioneffect{type=WITHER;d=1to999999;l=0to254} true 
                            ]} ~onTimer:20
```

1行の書き方：

```yaml
SkeletalKnight:
  Type: WITHER_SKELETON
  Skills:
  - damage{a=1} @PIR{r=10;conditions=[  - hasaura{aura=Plagued} true  - haspotioneffect{type=WITHER;d=1to999999;l=0to254} true ]} ~onTimer:20
```

## まとめ

| 書法 | 対象 | 説明 |
|------|------|------|
| `?condition` | キャスター | コンディションがtrueの場合 |
| `?!condition` | キャスター | コンディションがfalseの場合 |
| `?~condition` | トリガー | コンディションがtrueの場合 |
| `?~!condition` | トリガー | コンディションがfalseの場合 |
| `@targeter{conditions=[]}` | ターゲット | ターゲットコンディション（プレミアム） |
