
Input

```cr
module Example
  const TEN = 10 #=> scoreboard players set x constant 10

  as @s do
    tellraw "ten is #{TEN}" #=> tellraw @s ["ten is ",{"score":{"name":"@s","objective":"raycastCount"}}]
  end
end
```

<br>

Output

```cr
# main.mcfunction
execute as @a run function example:execute_as_s_1

# reset.mcfunction
scoreboard objectives add constant dummy
scoreboard players set x constant 10

# execute_as_s_1.mcfunction
tellraw @s run tellraw @s ["ten is ",{"score":{"name":"@s","objective":"raycastCount"}}]
```

