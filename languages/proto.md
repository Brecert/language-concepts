```
# assuming the inital syntax is nearly identical to crystal

# before
class Parser
  redef accept(Block) do |event, block|
    block.begin.accepts "do", Parser::None
    block.end.is "end"
    block.return.accepts block.expressions.last, "return"
  end
  
  redef accept(Def) do |event, def|
    def.begin.is "def"
  end
  
  redef accept(Call) do |event, call|
    call.args.begin.accepts "(".expects, Parser::None
  end
end

def add(one, two)
  one + two
end

add 1, 1 # => 2

# after
class Parser
  redef accept(Block) do |event : Event::Parser::Accept::Block, block : Parser::Node::Block|
    block.begin.is "{"
    block.end.is "}"
    block.return.is "return"
  end
  
  redef accept(Def) do |event, def|
    def.begin.is "function"
  end
end

function add(one, two) {
  return one + two
}

```
