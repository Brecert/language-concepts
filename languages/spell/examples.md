Initial.
```
if(block(redstone_block).position(below: 1).has?) then
  announce("Hello World!")
```

Translated.
```spell
si objectum redstone_block et lego statum sub I et magis tum nuntiare "Hello World"
```
```crystal
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



