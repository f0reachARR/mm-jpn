# @EntitiesNearOrigin (原点付近エンティティターゲッター)

## 概要
メタスキルの原点付近にいるすべてのエンティティをターゲットにします。`EntitiesInRadius` ターゲッターを継承しており、その属性をすべて使用できます。

- **タイプ**: 複数エンティティターゲッター
- **省略形**: `@NearOrigin`, `@ENO`

## 属性
> *固有の属性はありませんが、[EntitiesInRadius](/Skills/Targeters/EntitiesInRadius) の属性を使用できます*

## 使用例
```yaml
ExampleSkill:
  Skills:
  - projectile{...;
    onTick=[
      - effect:particles @origin
    ];
    onEnd=[
      - damage{a=10} @ENO{r=2}
      # プロジェクタイルが終了した時、原点から2ブロック以内のすべてのエンティティにダメージ
    ]} @target
```

## 備考
- `@EntitiesInRadius` はキャスター基準、こちらはスキルの原点（プロジェクタイルなど）基準です
- プロジェクタイルスキルと組み合わせて爆発範囲ダメージを実装するのに非常に便利です
