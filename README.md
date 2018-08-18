## 需要的插件

- [Rematch](https://www.curseforge.com/wow/addons/rematch)
- [tdBattlePetScript](https://www.curseforge.com/wow/addons/tdbattlepetscript)
- [tdBattlePetScript Rematch](https://www.curseforge.com/wow/addons/tdbattlepetscript-rematch)

## 配置

### 昆莱山-熊猫人雷霆之灵-2v3

Rematch `熊猫人雷霆之灵:22RH:2210DP:1220AJ:ZL:`

BattlePetScript
```
change(next) [ self.dead ]
if [ self(#1).active & enemy(#1).active ]
  ability(#1) [ enemy.round = 1 ]
  ability(#2) [ enemy.round = 2 ]
  ability(#1) [ enemy.round = 3 ]
  ability(#1) [ enemy.round = 4 ]
  ability(#1) [ enemy.round = 5 ]
  ability(#3) [ enemy.round = 6 ]
  ability(#1)
endif
if [ self(#1).active & enemy(#2).active ]
  ability(#2) [ enemy.round = 1 ]
  ability(#1) [ enemy.round = 2 ]
  ability(#1) [ enemy.round = 3 ]
  ability(#1) [ enemy.round = 4 ]
  ability(#3) [ enemy.round = 5 ]
  ability(#1)
endif
if [ self(#2).active & enemy(#2).active ]
  ability(#1)
endif
if [ self(#1).active & enemy(#3).active ]
  ability(#1)
endif
if [ self(#2).active & enemy(#3).active ]
  ability(#1) [ enemy.round = 1 ]
  ability(#3) [ enemy.round = 2 ]
  if [ enemy.hp < 618 ]
    ability(#2)
  endif
  ability(#1)
endif
```
### 锦绣谷-天选者亚济-2v3

Rematch `天选者亚济:215L:2124DU:122CAJ:ZL:`

BattlePetScript

```
change(next) [ self.dead ]
if [ self(#1).active & enemy(#1).active ]
  ability(#2) [ enemy.round = 1 ]
  ability(#3) [ enemy.round = 2 ]
  ability(#2) [ enemy.round = 3 ]
  ability(#1)
endif
if [ self(#1).active & enemy(#2).active ]
  ability(#2) [ enemy.round = 1 ]
  ability(#3) [ enemy.round = 2 ]
  ability(#1)
endif
if [ self(#2).active & enemy(#2).active ]
  ability(#1)
endif
if [ self(#1).active & enemy(#3).active ]
  ability(#1)
endif
if [ self(#2).active & enemy(#3).active ]
  ability(#3) [ enemy.round = 1 ]
  if [ enemy.hp < 618 & !enemy.ability(#2).usable & !enemy.ability(#3).usable & !enemy(#3).aura(生存).exists ]
    ability(#2)
  endif
  if [ enemy.hp > 250]
    ability(#1)
  endif
  standby
endif
```

### 寓言兽通用-3v3

Rematch `幸运的小艺:22UH:211414Q:222514S:21181FS:`

### 四风谷-农夫倪石-2v3

Rematch `农夫倪石:215E:1225QC:ZL:1228BV:P:200:1:::::`

BattlePetScript 

```
change(#1) [ self(#3).dead ]
change(next) [ self.dead ]
if [ self(#1).active & enemy(#1).active ]
  ability(#3) [ enemy.round = 1 ]
  change(#3)
endif
if [ self(#3).active & enemy(#1).active ]
  ability(#2) [ self.round = 1 ]
  ability(#3) [ self.round = 2 ]
  ability(#1) [ self.round = 3 ]
  ability(#3) [ self.round = 4 ]
  ability(#1)
endif
if [ self(#3).active & enemy(#2).active ]
  ability(#1) [ enemy.round = 1 ]
  ability(#3) [ enemy.round = 2 ]
  ability(#2) [ enemy.round = 3 ]
  ability(#3) [ enemy.round = 4 ]
  ability(#1)
endif
if [ self(#3).active & enemy(#3).active ]
  ability(#1) [ enemy.round = 1 ]
  change(#2) [ enemy.round = 2 ]
endif
if [ self(#2).active & enemy(#3).active ]
  change(#3)
endif
if [ self(#1).active & enemy(#3).active ]
  if [ enemy(#3).ability(#3).usable & self.ability(#3).usable ]
    ability(#3)
  endif
  ability(#1)
endif
```

### 卡桑琅丛林-莫鲁克-2v3

Rematch `莫鲁克:215D:122CAJ:2215HD:ZL:`

BattlePetScript

```
change(#1) [ self(#2).dead ]
change(next) [ self.dead ]
if [ self(#1).active & enemy(#1).active ]
  ability(#1) [ enemy.round = 1 ]
  ability(#3) [ enemy.round = 2 ]
  ability(#1)
endif
if [ self(#1).active & enemy(#2).active ]
  change(#2)
endif
if [ self(#2).active & enemy(#2).active ]
  if [ self.aura(昏睡).exists ]
    standby
  endif
  ability(#2) [ self.aura(韧性).exists ]
  ability(#3) [ !weather(月光) ]
  ability(#1) [ weather(月光) ]
  ability(#1) [ enemy.hp > 618 ]
  standby
endif
if [ self(#2).active & enemy(#3).active ]
  ability(#1)
endif
if [ self(#1).active & enemy(#3).active ]
  if [ enemy.hp < 618 ]
    ability(#2)
  endif
  ability(#1)
endif
```

### 恐惧废土-熊猫人流水之灵-2v3

Rematch `熊猫人流水之灵:22RE:1124GM:1219R4:ZL:P:650::9::::`

BattlePetScript

```
change(next) [ self.dead ]
if [ self(#1).active & enemy(#1).active ]
  ability(#2) [ enemy.round = 1 ]
  ability(#1) [ enemy.round = 2 ]
  ability(#3) [ enemy.round = 3 ]
  ability(#1)
endif
if [ self(#1).active & enemy(#2).active ]
  ability(#1)
endif
if [ self(#1).active & enemy(#3).active ]
  if [ !self(#3).played ]
    change(#3)
  endif
  ability(#3) [ self.aura(喷泉).duration = 1 & self.aura(湍流旋涡).duration = 1 ]
  ability(#1)
endif
if [ self(#3).active & enemy(#3).active ]
  change(#1)
endif
```

### 恐惧废土-废土行者苏游-2v3

Rematch `废土行者苏游:215J:2114F9:122CAJ:ZL:`

BattlePetScript

```
change(next) [ self.dead ]
if [ self(#1).active & enemy(#1).active ]
  ability(#3) [ enemy.round = 4 ]
  ability(#1)
endif
if [ self(#1).active & enemy(#2).active ]
  ability(#2) [ enemy.round = 2 ]
  ability(#1)
endif
if [ self(#1).active & enemy(#3).active ]
  ability(#1)
endif
if [ self(#2).active & enemy(#2).active ]
  ability(#1)
endif
if [ self(#2).active & enemy(#3).active ]
  ability(#2) [ enemy.hp < 618 ]
  ability(#1)
endif
```

### 螳螂高原-探索者祖什-2v3

Rematch `探索者祖什:21B6:1216EF:21244C:ZL:`

BattlePetScript

```
change(next) [ self.dead ]
if [ self(#1).active & enemy(#1).active ]
  ability(#2) [ enemy.round = 1 ]
  ability(#1)
endif
if [ self(#1).active & enemy(#2).active ]
  ability(#1) [ enemy.round = 1 ]
  ability(#2) [ enemy.round = 2 ]
  ability(#1)
endif
if [ self(#2).active & enemy(#2).active ]
  ability(#1)
endif
if [ self(#2).active & enemy(#3).active ]
  ability(#3) [ enemy.round = 1 ]
  change(#3) [ enemy.round = 2 & !self(#3).played ]
  ability(#2) [ self.round = 1 & enemy.round != 1 ]
  ability(#1)
endif
if [ self(#3).active & enemy(#3).active ]
  change(#2)
endif
```

### 螳螂高原-熊猫人烈焰之灵-2v3

Rematch `熊猫人烈焰之灵:22RF:1216EF:1126140:ZL:P:600::::::`

BattlePetScript

```
change(next) [ self.dead ]
if [ self(#1).active & enemy(#1).active ]
  ability(#3) [ enemy.round = 1 ]
  ability(#2) [ enemy.round = 2 ]
  ability(#1)
endif
if [ self(#1).active & enemy(#2).active ]
  ability(#2) [ self.ability(#2).usable ]
  ability(#1)
endif
if [ self(#1).active & enemy(#3).active ]
  change(#3) [ !self(#3).played ]
endif
if [ self(#3).active & enemy(#3).active ]
  change(#2)
endif
if [ self(#2).active & enemy(#3).active ]
  ability(#2) [ !enemy.aura(嚎叫).exists & self.ability(#2).usable ]
  ability(#3) [ enemy.aura(嚎叫).exists ]
  ability(#1)
endif
```

### 昆莱山-勇敢的尹勇-2v3

Rematch `勇敢的尹勇:215I:122CAJ:2115HD:ZL:`

BattlePetScript

```
change(#1) [ self(#2).dead ]
change(next) [ self.dead ]
if [ self(#1).active & enemy(#1).active ]
  ability(#3) [ enemy.round = 1 ]
  change(#2) [ !self(#2).played ]
endif
if [ self(#2).active & enemy(#1).active ]
  ability(#3) [ self.round = 1 ]
  ability(#1)
endif
if [ self(#2).active & enemy(#2).active ]
  ability(#1) [ enemy.round = 1 ]
  ability(#2) [ enemy.round = 2 ]
  ability(#1)
endif
if [ self(#2).active & enemy(#3).active ]
  ability(#1)
endif
if [ self(#1).active & enemy(#3).active ]
  ability(#2) [ enemy.hp < 618 ]
  ability(#1)
endif
```

### 翡翠林-熊猫人微风之灵-2v3

Rematch `熊猫人微风之灵:22RG:2215HD:1219R4:ZL:`

BattlePetScript

```
change(next) [ self.dead ]
if [ self(#1).active & enemy(#1).active ]
  quit [ self.aura(昏睡).exists ]
  ability(#3) [ enemy.round = 1 ]
  ability(#1)
endif
if [ self(#1).active & enemy(#2).active ]
  ability(#2) [ enemy.round = 1 ]
  ability(#1)
endif
if [ self(#1).active & enemy(#3).active ]
  change(#3) [ !self(#3).played ]
endif
if [ self(#3).active & enemy(#3).active ]
  change(#2) [ !self(#2).played ]
endif
if [ self(#2).active & enemy(#3).active ]
  ability(#3) [ self.round = 1 ]
  ability(#2) [ self.round = 2 ]
  ability(#1)
endif
```

### 达拉然-阿玛利亚-2v3

Rematch `阿玛利亚:38V1:122CAJ:ZL:1228BV:`

BattlePetScript

```
change(next) [ self.dead ]
if [ self(#1).active & enemy(#1).active ]
  ability(#1)
endif
if [ self(#1).active & enemy(#2).active ]
  ability(#3) [ enemy.round = 1 ]
  ability(#1)
endif
if [ self(#1).active & enemy(#3).active ]
  ability(#2)
endif
if [ self(#2).active & enemy(#2).active ]
  quit
endif
if [ self(#2).active & enemy(#3).active ]
  change(#3)
endif
if [ self(#3).active & enemy(#3).active ]
  ability(#3) [ enemy.hp < 300 ]
  ability(#3)
endif
```

### 达拉然-加尔维斯顿先生-2v3

Rematch `加尔维斯顿先生:30RE:2215HD:1215G2:ZL:`

BattlePetScript

```
change(next) [ self.dead ]
if [ self(#1).active & enemy(#1).active ]
  ability(#3) [ enemy.round = 1 & !weather(月光) ]
  ability(#2) [ enemy.round = 2 ]
  ability(#3)
endif
if [ self(#1).active & enemy(#2).active ]
  ability(#1)
endif
if [ self(#2).active & enemy(#1).active ]
  change(#3)
endif
if [ self(#3).active & enemy(#3).active ]
  ability(#3) [ enemy.round = 1 ]
  ability(#2) [ enemy.round = 2 ]
  ability(#1)
endif
if [ self(#3).active & enemy(#1).active ]
  ability(#3) [ enemy.round = 1 ]
  ability(#1) [ enemy.round = 2 ]
  ability(#2) [ enemy.round = 3 ]
  ability(#1) [ enemy.round = 4 ]
  ability(#3) [ enemy.round = 5 ]
  ability(#1) [ enemy.round = 6 ]
endif
```



### 破碎海滩-无名秘术师-2v3

Rematch `无名秘术师:3J5V:1225QC:12292L:ZL:`

BattlePetScript

```
change(next) [ self.dead ]
if [ self(#1).active & enemy(#1).active ]
  ability(#2) [ enemy.round = 1 ]
  ability(#3) [ enemy.round = 2 ]
  ability(#1)
endif
if [ self(#1).active & enemy(#2).active ]
  ability(#2) [ self.ability(#2).usable ]
  ability(#1)
endif
if [ self(#1).active & enemy(#3).active ]
  ability(#3) [ enemy.round = 1 ]
  ability(#2) [ self.ability(#2).usable ]
  ability(#1) [ enemy.hp > 650 ]
  standby
endif
if [ self(#2).active & enemy(#3).active ]
  ability(#3)
endif
```

### 要塞-斯奎特-2v3

Rematch `斯奎特:2DAB:2215HD:1218E8:ZL:`

BattlePetScript

```
change(next) [ self.dead ]
if [ self(#1).active & enemy(#1).active ]
  ability(#3) [ !weather(月光) ]
  ability(#1)
endif
if [ self(#1).active & enemy(#2).active ]
  ability(#2) [ enemy.round = 1 ]
  ability(#3) [ !weather(月光) & self.ability(#3).usable ]
  ability(#1)
endif
if [ self(#2).active & enemy(#2).active ]
  ability(#2) [ enemy.hp < 970 ]
  ability(#1)
endif
if [ self(#2).active & enemy(#3).active ]
  change(#3) [ !self(#3).played ]
  ability(#2) [ enemy.hp < 1200 ]
  ability(#1)
endif
if [ self(#3).active & enemy(#3).active ]
  change(#2)
endif
```

### 要塞-挑战木桩-三鸟-1v3

Rematch `挑战木桩-三鸟:2JJR:12281LP:12281LP:2215HD:`

BattlePetScript

```
change(next) [ self.dead ]
ability(#3) [ self.ability(#3).usable & !enemy(#2).active ]
ability(#2) [ self.ability(#2).usable ]
ability(#1)
```



## 协议

本文章所有内容均在 [CC-BY-NC 4.0](https://creativecommons.org/licenses/by-nc/4.0/) 许可下发布。 