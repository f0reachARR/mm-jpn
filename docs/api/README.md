# API情報 (API)

MythicMobsはJava APIとPlaceholderAPI統合を提供しており、他のプラグイン開発者がMythicMobsと連携できます。

## Maven/Gradleの依存関係

Mavenを使用している場合:

```xml
<repositories>
    <repository>
        <id>lumine-releases</id>
        <url>https://mvn.lumine.io/repository/maven-public/</url>
    </repository>
</repositories>

<dependencies>
    <dependency>
        <groupId>io.lumine</groupId>
        <artifactId>Mythic-Dist</artifactId>
        <version>5.9.x-SNAPSHOT</version>
        <scope>provided</scope>
    </dependency>
</dependencies>
```

Gradleを使用している場合:

```groovy
repositories {
    maven { url 'https://mvn.lumine.io/repository/maven-public/' }
}

dependencies {
    compileOnly 'io.lumine:Mythic-Dist:5.9.x-SNAPSHOT'
}
```

## 基本的なAPI使用方法

### MythicMobsインスタンスの取得

```java
MythicBukkit mythicMobs = MythicBukkit.inst();
```

### モブのスポーン

```java
// 特定の場所にMythicMobをスポーン
MythicBukkit api = MythicBukkit.inst();
Location location = // スポーン場所;
Optional<ActiveMob> mob = api.getMobManager().spawnMob("SkeletonKing", location);
```

### MythicMobのチェック

```java
Entity entity = // 確認したいエンティティ;
if (MythicBukkit.inst().getMobManager().isActiveMob(entity.getUniqueId())) {
    ActiveMob activeMob = MythicBukkit.inst().getMobManager()
        .getActiveMob(entity.getUniqueId()).orElse(null);
    if (activeMob != null) {
        String mobType = activeMob.getMobType();
        // mobTypeを使って何かする
    }
}
```

### カスタムスキルの登録

```java
MythicBukkit.inst().getSkillManager().register(new MyCustomSkill());
```

## イベント

MythicMobsはBukkitイベントシステムを使用して以下のイベントを提供します：

| イベント | 説明 |
|--------|------|
| `MythicMobSpawnEvent` | MythicMobがスポーンするときに発生 |
| `MythicMobDeathEvent` | MythicMobが死亡するときに発生 |
| `MythicMobDespawnEvent` | MythicMobがデスポーンするときに発生 |
| `MythicSkillCastEvent` | MythicMobがスキルをキャストするときに発生 |
| `MythicConditionLoadEvent` | コンディションがロードされるときに発生 |
| `MythicMechanicLoadEvent` | メカニクスがロードされるときに発生 |
| `MythicTargeterLoadEvent` | ターゲッターがロードされるときに発生 |

## カスタムメカニクスの作成

```java
public class MyCustomMechanic extends AbstractMechanic {
    
    @MythicMechanic(name="myMechanic", aliases={"myAlias"})
    public MyCustomMechanic(MythicLineConfig mlc) {
        super(mlc);
        // 設定を読み込む
    }
    
    @Override
    public boolean cast(SkillMetadata skillMetadata) {
        // メカニクスロジックを実装
        return true;
    }
}
```

## PlaceholderAPIとの統合

MythicMobsはPlaceholderAPIと統合されており、以下のプレースホルダーが外部プラグインで使用できます：

```
%mythicmobs_mythictype%    # プレイヤーのMythicMobタイプ（MythicMobの場合）
%mythicmobs_hp%            # プレイヤーのHP
%mythicmobs_mhp%           # プレイヤーの最大HP
```

## サブページ

- [プレースホルダーAPI](placeholders-api.md)
- [カスタムコンディション](custom-conditions.md)
- [カスタムメカニクス](custom-mechanics.md)
- [カスタムターゲッター](custom-targeters.md)
