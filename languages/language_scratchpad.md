puts | say | log
print | whisper

1 + 1
1.+(1)

if 1 < 10
if(1.<(10))

if returns a conditional object

def do()
  yield
end

if(true).do
  blockety block
  
loops are special iterations

class While < Loop
  when started do
  (backend for loop)
    yield
  (backend end)
  end
  
  _With methods you can make them accept anything, even non-defined objects._
  instance.method(do)
    _! is basically self_
    !.start
  end
end

```rb
method(say)
  "{{say ~if(~.object?).&(not(~.nil?)).do(~.to_s) }}"
end
```

cleared up one piece at a time

`".()`

`".( {{(say)`

_{{ is just a method/class that works similar to #{}, but more macro like_

_Similary to crystal I suppose_

https://crystal-lang.org/docs/syntax_and_semantics/macros.html

`".( {{ say.~.if`

_~ is a special object, it makes things truely inline by using the class that instanced it_

_with this, it makes ~if like an inline, inline if_

`".( {{ say ~if( ~.object?`

_Because nothing is instancing it, it simply uses the last instanced class, which would be say, because say instanced ~.if_

`".( {{ say ~if( ~.object? ).&`

_If returns a conditional class, the class has .& which is just && in ruby._

`".( {{ say ~if( ~.object? ).&( not(~.nil?)`

_Not is just a method that reversed what it's given, the equivlent of !_

`".( {{ say ~if( ~.object? ).&( not(~.nil?).do(`

_.do is just a method, so of course it can be done inline_

`".( {{ say ~if( ~.object? ).&( not(~.nil?).do(~.to_s)`

_By doing .do, the conditional class is finalized and what is returned by do, is returned to parent classes_

_In this case by doing ~.to_s and calling the last class (say), it returns (say).to_s_

_Do is not needed because it already yeilds, but do can be used_

By doing all of this, say can do many things in a simple way.
Say can recieve direct input `say(Hi!)`, and say can recieve objects, `say(Object)` (including strings)

while(true)
  say(hi)
end

say Hello! if username is not Brecert

say(Hello!).if(username).is(not(Brecert))

echo Hello
echo(Hello)

In shell everything is typically a string unless otherwise specified.
In other languages, everything is a token/object unless otherwise specified.

How would I mix them in a fast, readable format.
Perhaps a mix of both where you change modes.

```cr
`use code`
def say(string : String)
  puts string
end

local string world = "World"

`use text`
say Hello!
```
Using the variables are confuing, perhaps there could be different insertion modes.
```cr
`use crystal text`
say Hello #{world}!
# or
`use shell text`
say Hello %world%
# or
`use javascript text`
say Hello ${world}
# or
`use custom '{{' '}}'`
say hello {{world}}
```

What if you could define the syntax of a function, so that you could do special things with it.

```cr
ignoring interpreter define say(text : Raw(
  ending: '...', '.', '?!', '!?', '?', '!'
)) do
  puts text.to_s().remove_commas().template(begin: '#{', end: '}')
end


# The language needs to trust you that this works.
# Lots of sharp edges.

say(Hello World!)
# => "Hello World"

say(Hi)
# => Error Expected ..., ., ?!, !?, ?, or !

# Doesn't work with objects because it just takes raw input, no handling.
# It's also expecting it to end with a specific ending, objects tend not to do that.
# The ending needs to happen, even if it's `\n` or similar, unless you have a decent lex/parse/interp
say(object)
# => Error Expected ..., ., ?!, !?, ?, or !

say(I, don't, like, commas...)
# => "I don't like commas..."

string public ≠ = "do not"
say(I, really, #{≠} like, commas)
# => "I really do not like commas"
# Works because of .template that happens after the raw text is entered.
# A this is meant to show how powerful it is.
# Even though its a very sharp edge.
```

------

```cr
# From
put("Hello world").in(the(STD::Out))
# To
put "Hello world in the STD::Out
# To
put "Hello World" in the Standard::Out
```

```cr
public string "String" << ~
print string
# Never happens, string inserts into itself forever.
```

```cr
# Gate based programming (already a thing but forgot name)

# NOT
# AND
# OR
# NAND
# NOR
# XOR
# XNOR

# TIMER / CLOCK

local undefined wire

wire >> NOT >> TIMER(ms) >> wire
wire >> SAY("Hello World!")
```
basically
```cr
# wire goes into not
wire >> NOT
# not goes into a timer
NOT >> TIMER(1s)
# timer counts up to 1 and goes back into wire
TIMER(1s) >> wire
# loop happens

# When wire is activated, say hello world!
wire >> SAY("Hello World!")
# => "Hello World!"
```

```cr
# Example


NOT >> WIRE >> SAY("Hello World!")
 ^      V
 ^      V
TIMER(1s)

# Not by default is turned on. (because it reverses), like how !false == true
# Not outputs to the wire/node, the wire/node outputs into the timer
# The timer counts up to 1s when it recieves input
# When the timer reaches 1s it sends a truthy to NOT ans NOT powers off.
# Assuming the timer resets when it's full, NOT just flickers off for a moment before turning on.
# When it turns on again it activate SAY
# It loops forever since there is no end.
# Basic program
# Just logic gates put on here.
```

| ! | > | v                    |   |   |
|---|---|----------------------|---|---|
| ^ |   | PUTS("Hello World!") |   |   |
| ^ |   | <                    |   |   |
|   |   |                      |   |   |

       


