### Test

```cr
module Click
  clicked = path("minecraft.used:minecraft.carrot_on_a_stick")
  
  def on_click
    say "pew pew"
  end
  
  as @a do
    if clicked >= 1
      # function path("click:on_click")
      on_click
    end
    
    clicked = 0
  end
end
```
<br>

Output

```mcfunction
# main.mcfunction
execute as @a run function rightclick:as/a/1

# reset.mcfunction
scoreboard objectives remove clicked minecraft.used:minecraft.carrot_on_a_stick
scoreboard objectives add clicked minecraft.used:minecraft.carrot_on_a_stick

# on_click.mcfunction
say pew pew

# as/a/1.mcfunction
execute if score @s clicked matches 1.. run function click:on_click
scoreboard players set @s clicked 0
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

