```
# assuming the inital syntax is nearly identical to crystal

# before
def add(one, two)
  one + two
end

add 1, 2

# is a macro
Parser::Def.def.redef %("function" args? Block)
Parser::Block.redef %(begin:"{" Expressions "}")
Parser::args.redef %("(" argList ")")


# after
function add(one, two) {
  return one + two
}

add(1, 2)

```
