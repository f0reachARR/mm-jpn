# Rally（集結）

## 説明

近くの他のモブをターゲットに攻撃させます。

## 属性

| 属性 | エイリアス | 説明 | デフォルト値 |
|-----------|-----------|----------------------------------------------------------------------|---------|
| types | type, t | A list of mob types to rally. The list can include both Mythic Mob types and regular Entity types | <!--type:Mob--><!--list--> |
| radius | r, hradius, hr | ターゲット周囲の半径 | 10 |
| vradius | vr | Overrides the vertical component of the radius. | radius |
| overwritetarget | ot | するかどうか | true |
| rallyconditions | conditions, cond, c | A list of conditions that the entities must pass in order to be rallied | <!--type:Conditions--> |
