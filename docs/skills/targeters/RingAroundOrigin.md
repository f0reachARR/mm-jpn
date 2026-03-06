# @RingAroundOrigin (原点周囲リングターゲッター)

## 概要
スキルの原点を中心としたリング（円）上の位置をターゲットにします。回転はラジアン単位です（90度 = 1.57）。

- **タイプ**: 複数場所ターゲッター
- **省略形**: `@ringOrigin`, `@RAO`

## 属性
| 属性 | 省略形 | 説明 | デフォルト |
|------|--------|------|-----------|
| radius | r | リングの半径（ブロック数） | 5 |
| points | p | リングを構成するポイント数 | 10 |
| rotationx | rotx, rx | X軸の回転（ラジアン） | 0 |
| rotationy | roty, ry | Y軸の回転（ラジアン） | 0 |
| rotationz | rotz, rz | Z軸の回転（ラジアン） | 0 |
| offsetx | offx, ox | X軸のオフセット | 0 |
| offsety | offy, oy | Y軸のオフセット | 0 |
| offsetz | offz, oz | Z軸のオフセット | 0 |
| relative | | リングの向きをキャスターに対して相対的にするか | false |

## 使用例
```yaml
ExampleSkill:
  Skills:
  - projectile{...;
    onEnd=[
      - effect:particles @RingAroundOrigin{r=5;p=15}  # 終了時、原点を中心に半径5のリングにパーティクル
    ]}

# 垂直なリングを描く場合（Z軸を90度回転）
VerticalRingSkill:
  Skills:
  - particles{p=enchanted_hit;a=1;} @RAO{r=2;rz=1.57;p=9;relative=true}
```

## 備考
- `@Ring` はキャスター基準、こちらはスキルの原点基準です
- `rz=1.57`（90度）を使用すると垂直なリングになります
