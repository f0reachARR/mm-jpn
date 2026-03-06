# 脅威テーブル (Threat Tables)

脅威テーブルはモブのターゲッティング動作に強化されたコントロールを付与し、RPGの敵に似た動作をモブに可能にします。脅威テーブルが有効なモブは、どのエンティティを優先するかを決定するために「脅威」の内部リストを保持します。

## 有効化

脅威テーブルはモブのModulesセクションで有効にできます：

```yaml
example_mob:
  Type: husk
  Modules:
    ThreatTable: true
```

または、Optionsセクションでも：

```yaml
example_mob:
  Type: husk
  Options:
    UseThreatTable: true
```

## 脅威テーブルの仕組み

脅威テーブルが有効なモブの場合：

1. プレイヤーがモブにダメージを与えると、脅威が増加します
2. プレイヤーがモブを癒したり、バフを与えたりすると、その効果に対して脅威が増加します
3. モブは最高の脅威を持つエンティティをターゲットにします
4. 脅威テーブルに基づいた追加のトリガーが利用可能になります

## 脅威テーブルと連動するトリガー

| トリガー | 説明 |
|--------|------|
| [onEnterCombat](../skills/triggers/onEnterCombat.md) | モブが戦闘に入ったとき（脅威テーブルが必要） |
| [onDropCombat](../skills/triggers/onDropCombat.md) | モブが戦闘を離れたとき（脅威テーブルが必要） |
| [onChangeTarget](../skills/triggers/onChangeTarget.md) | モブがターゲットを変更したとき（脅威テーブルが必要） |

## 脅威操作メカニクス

| メカニクス | 説明 |
|---------|------|
| AddThreat | ターゲットの脅威を増加させます |
| ReduceThreat | ターゲットの脅威を減少させます |
| ClearThreat | モブの脅威テーブルをクリアします |
| TransferThreat | 脅威を1つのエンティティから別のエンティティに移します |

## 脅威テーブルと連動するAIターゲッター

- **ThreatTable**: 脅威テーブル内のすべてのエンティティをターゲットにします
- **ThreatTablePlayers**: 脅威テーブル内のすべてのプレイヤーをターゲットにします

## 例

```yaml
TankMob:
  Type: ZOMBIE
  Options:
    UseThreatTable: true
  AITargetSelectors:
  - clear
  - ThreatTable  # 脅威テーブルからターゲットを選択
  Skills:
  - message{m="<caster.tt.top>が最も脅威的だ！"} @self ~onChangeTarget
  - addthreat{amount=10} @ThreatTablePlayers ~onAttack
```
