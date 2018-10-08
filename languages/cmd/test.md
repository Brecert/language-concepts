```cr
const TEN = 10 #=> scoreboard players set x constant 10

tellraw @s, "ten is #{TEN}" #=> tellraw @s ["ten is ",{"score":{"name":"@s","objective":"raycastCount"}}]
```
