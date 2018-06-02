Self extending language

Quick Example with a Ruby syntax.
```rb
HTML::Builder.build
  div.name do
    nav.bar do
      a src="hello"
    end
  end
end
```
Div, nav, a are not defined.
The methods, .name, .bar, are not defined
The argument, src is not defined.

So how would this all work?

The idea of the language is that the Language Syntax adapts to you.
You do not adapt to the language.

Even in languages like Python or Ruby there is a limit to how much you can modify and ease the syntax.
There should be no limit like that.

If I say the language should now suddenly use the 'x' symbol for multiplication instead of '*', that should be allowed, very simply.
```rb
event Parser::Expecting do |token|
  if token == "Multiply"
    token.value = 'x'
  end
end
```
_of course this syntax is bad and a little weird and should be tweaked to be more to make more sense but ignore that for now_

This may be confusing at first, as the parser would not follow conventional ways of doing things.
For now stop thinking about how the parser would have to work, and think about how easy it would be.

If a language was created in this way, that everything could be modified while running, it could create a new way to code not only languages, but code (in general)

Preprocessors would be great for this.
So many of them re-implement basic programming features such as variables, conditionals, loops etc...
Why re-implement it when you can just extend a base language in a much simpler way.









