## 需要的插件

- [Rematch](https://www.curseforge.com/wow/addons/rematch)
- [tdBattlePetScript](https://www.curseforge.com/wow/addons/tdbattlepetscript)
- [tdBattlePetScript Rematch](https://www.curseforge.com/wow/addons/tdbattlepetscript-rematch)

## 配置

### 昆莱山-熊猫人雷霆之灵-2v3

Rematch 队伍配置：`熊猫人雷霆之灵:22RH:2210DP:1220AJ:ZL:`

BattlePetScript：
```
change(next) [ self.dead ]
if [ self(#1).active & enemy(#1).active ]
  ability(#1) [ enemy.round=1 ]
  ability(#2) [ enemy.round=2 ]
  ability(#1) [ enemy.round=3 ]
  ability(#1) [ enemy.round=4 ]
  ability(#1) [ enemy.round=5 ]
  ability(#3) [ enemy.round=6 ]
  ability(#1)
endif
if [ self(#1).active & enemy(#2).active ]
  ability(#2) [ enemy.round=1 ]
  ability(#1) [ enemy.round=2 ]
  ability(#1) [ enemy.round=3 ]
  ability(#1) [ enemy.round=4 ]
  ability(#3) [ enemy.round=5 ]
  ability(#1)
endif
if [ self(#2).active & enemy(#2).active ]
  ability(#1)
endif
if [ self(#1).active & enemy(#3).active ]
  ability(#1)
endif
if [ self(#2).active & enemy(#3).active ]
  ability(#1) [ enemy.round=1 ]
  ability(#3) [ enemy.round=2 ]
  if [ enemy.hp < 608 ]
    ability(#2)
  endif
  ability(#1)
endif
```