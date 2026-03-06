# カスタムAI (Custom AI)

MythicMobs では、`AIGoalSelectors` と `AITargetSelectors` を使用してモブのAI行動を細かく制御できます。

---

## 概要

Minecraft のモブは「ゴール」と「ターゲット」という2つのAIシステムで制御されています：
- **AIGoalSelectors**: モブが何をするか（移動、攻撃、逃げるなど）
- **AITargetSelectors**: モブが何をターゲットにするか

---

## 基本構文

```yaml
MobName:
  AIGoalSelectors:
  - <優先度> <ゴール>[{オプション}]
  AITargetSelectors:
  - <優先度> <ターゲット>[{オプション}]
```

優先度は数字で、**小さいほど高い優先度**で実行されます。

---

## AIGoalSelectors（行動ゴール）

### ゴール一覧

| ゴール | 説明 |
|--------|------|
| `clear` | デフォルトのAIをすべてクリア |
| `meleeattack` | 近接攻撃を行う |
| `rangedattack` | 遠距離攻撃を行う |
| `randomstroll` | ランダムに歩き回る |
| `randomlook` | ランダムな方向を見る |
| `look` | ターゲットの方向を見る |
| `float` | 水に浮く |
| `flee` | プレイヤーから逃げる |
| `opendoor` | ドアを開ける |
| `breaddoor` | ドアを壊す |
| `leapattarget` | ターゲットに向かってジャンプ攻撃する |
| `avoidplayers` | プレイヤーを避ける |
| `followowner` | オーナー（テイム主）を追いかける |
| `followmob` | 他のモブを追いかける |
| `stayclose` | 特定の場所に留まる |
| `returntospawn` | スポーン地点に戻る |

### ゴールのオプション例

```yaml
AIGoalSelectors:
- 0 clear
- 1 meleeattack{speed=1.0;when=FIGHTING}
- 2 randomstroll{speed=0.6}
- 3 look{range=8}
- 4 float
```

---

## AITargetSelectors（ターゲット選択）

### ターゲット一覧

| ターゲット | 説明 |
|-----------|------|
| `clear` | デフォルトのターゲットをクリア |
| `players` | プレイヤーをターゲット |
| `monsters` | モンスターをターゲット |
| `animals` | 動物をターゲット |
| `golems` | ゴーレムをターゲット |
| `villagers` | 村人をターゲット |
| `notself` | 自分以外のエンティティをターゲット |
| `target` | 現在のターゲットを維持 |
| `attacker` | 攻撃者をターゲット |
| `faction{f=<派閥>}` | 指定した派閥をターゲット |
| `notfaction{f=<派閥>}` | 指定した派閥以外をターゲット |
| `mythicmob` | MythicMobs のモブをターゲット |

---

## 設定例

### 基本的なボスAI

```yaml
BossZombie:
  Type: ZOMBIE
  Display: "&4ボスゾンビ"
  Health: 500
  AIGoalSelectors:
  - 0 clear
  - 1 meleeattack
  - 2 randomstroll
  - 3 look
  - 4 float
  AITargetSelectors:
  - 0 clear
  - 1 players
  - 2 golems
```

### 逃げ回るモブ

```yaml
CowardMob:
  Type: CHICKEN
  Display: "臆病者"
  Health: 20
  AIGoalSelectors:
  - 0 clear
  - 1 flee
  - 2 randomstroll
  - 3 float
  AITargetSelectors:
  - 0 clear
  - 1 players
```

### 派閥間戦闘

```yaml
UltraKnight:
  Type: ZOMBIE
  Faction: DarkArmy
  AIGoalSelectors:
  - 0 clear
  - 1 meleeattack
  - 2 randomstroll
  AITargetSelectors:
  - 0 clear
  - 1 players
  - 2 faction{f=HolyOrder}
```

---

## 注意事項

- `0 clear` を最初に入れることで、バニラのAI設定をリセットできます。
- AIゴールの順序（優先度）は動作に大きく影響します。
- 一部のゴールはエンティティタイプによって動作しない場合があります。

---

[← モブ設定に戻る](Mobs.md) | [← ホームに戻る](../Home.md)
