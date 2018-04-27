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
`"(1 + 1 = #{.(1 + 1).})."

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

_ignore this for now | while(true).do(yield).end_
