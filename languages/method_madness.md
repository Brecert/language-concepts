Take everything is an object and combine it with everything that is a class is a method, and everything that is a method is class.
Nothing is done by the compiler. (if done right)
Example.
In ruby a string can be made by
`"I'm a string!"`
In this it can be made the same way, however the way it works is different.
`"I'm a string"`
Here's how it works
`".(I'm a string)."`

In ruby templates are handled like this, by the interpreter.
`"1 + 1 = #{1 + 1}"`

In this it works the same but like this.
`"(1 + 1 = #{.(1 + 1).})."`

You may be wondering about the ." or .}
It's the same as an `end` in ruby, but again, it's a method, and because it's a method, it can be redefined and renamed.

The source of a really basic way of making strings might look like this.

```rb
class Do
  # skip everything until important
  def end
    # (end stuff)
  end
end

class String
  
  extend class Do
    redef end as " (inherit)
      inherit
    end
  end

  # Obviously have some way for the interpreter to know that " is the name, but ignore all of that right now.
  def " (**args)
    new String(yield self.do(args))
  end
end
```

With that code a string would be instanced with `"(code)` and ended with the `."` method

This is what I mean by everything is a method, nothing is handled directly by the interpreter.
It would be extremely slow, but would allow for some amazing metaprogramming.

You could redefine the entire language inside of itself if you wanted to...

Instead of instancing string with `"` to start and end it why not `Begin Sentence\s` and `\sEnd of Sentence` so it would be `Begin Sentence Hello World! End of Sentence`

The base language itself would have nothing in it other then the parser and basic interpreter for all of this.
However standard definitions like `def` and things like that wouldn't actually be defined inside of the interpreter.
It would be specially defined separately in a language/definitions library, presumably coded with bindings to C or LLVM.
This way the langauge could be styled however you wanted.
Python syntax (not whitespace though) or Ruby, maybe C or JS, just change the names of begin and end for most things.


_ignore this for now | while(true).do(yield).end_
