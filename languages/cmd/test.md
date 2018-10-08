### Test

```cr
module RightClick
  clicked = path("minecraft.used:minecraft.carrot_on_a_stick")
  
  def on_click
    say "pew pew"
  end
  
  as @a do
    if clicked >= 1
      # function path("rightclick:on_click")
      on_click
    end
  end
  
  clicked = 0
end
```
<br>

### Constants

Input

```cr
module Example
  const TEN = 10 #=> scoreboard players set x constant 10

  as @a do
    tellraw "ten is #{TEN}" #=> tellraw @s ["ten is ",{"score":{"name":"TEN","objective":"constant"}}]
  end
end
```

<br>

Output

```mcfunction
# main.mcfunction
execute as @a run function example:as/a/1

# reset.mcfunction
scoreboard objectives add constant dummy
scoreboard players set x constant 10

# as/a/1.mcfunction
tellraw @s run tellraw @s ["ten is ",{"score":{"name":"TEN","objective":"constant"}}]
```

