Initial.
```
if(block(redstone_block).position(below: 1).has?) then
  announce("Hello World")
```
Translated to natural english. Optionals in \[], Default arguments that aren't used are in \[()]
```
if block [is] [a] redstone_block position[ed] below [(self)] 1 [is true] then announce "Hello World"
```

Without any optionals
```
if block redstone_block position below 1 then announce "Hello World!"
```

Translated.
```spell
si objectum redstone_block et lego statum sub I et magis tum nuntiare "Hello World"
```
```yaml
if       : si
objectum : block|object
et       : .|is|has
lego     : :|selector
statum   : position
sub      : below|underneath
I        : 1
et       : .|is|has
magis    : ?|!!|truer|bool
tum      : then
nuntiare : announce
```
___

```
when "hello" is said then reply with "Hello world!"
```
```
when "hello" said reply "Hello World!"
```
```
when(said, "Hello") { reply("Hello World") }
```
```
event(Event::Said, "Hello") { |self| self.reply("Hello World") }
```
```
quod logos heus responsio salve
```

