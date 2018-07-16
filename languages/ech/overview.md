# The "Language" stuff.
> This is just the basics of the language
>
> It's not complicated and is meant to be kind of uselss on its own
>
> If you want a real language use a real language.
>
> The real part of the language is the html portion of it, all of this is fluff and the actual language could function without most of this.

## variable
```hs
project_name : String
project_name <- "ech-lang"
projects : Array(String)
projects <- [] << project_name
```

## normal, global, private, const
```
 hello  : String `normal (let)`
@hello  : String `global (var)`
~hello  : String `private`
 HELLO  : String `const (const)`
```

## function/method
### just a variable with 'piping'
```
add <- (number1, number2) -> 
  return number1 + number2
```
  
## methods can be overloaded with different arguments and argument types
```
add <- (number1 : Number, number2 : Number) ->
  return number1 + number2
  
add <- (array1 : Array, array2 : Array) ->
  retunr array1 << array2
  
numbers : Array(Number)
numbers <- [10, 20, 30, 40]

foods : Array(String)
foods <- ["sushi", "pasta", "steak"]

add(10, 15) `25 : Number`
add(numbers, foods) `[10, 20, 30, 40, "sushi", "pasta", "steak"] : Array(Number | String)`
```

  
## normal, global, private, const can be used on functions/methods
### private add method
```
~add <- (number1, number2) ->
  return number1 + number2
 ```
  
## class
### uses private methods for special methods like init
```
String <- (Class) ->
  ~init <- (string : String) ->
    @string : Array(Char)
    @string <- string
    return self
```
  
  
  
  
  
  
  
