```cr
MAX   = 1.0
MID   = 0.0
MIN   = -1.0

TRUE  = MAX
FALSE = MID

Node
  inputs  : Int
  outputs : Int
  
  def run
    return input
  end
end
  
Not < Node
  inputs : 1
  outputs: 1
  
  input[0].name = ""
  
  def run
    for input in inputs do |index|
      output[index]  = !input.value
    end
  end
end

And < Node
  inputs : 2
  outputs : 1
  
  properties = {
    inputs: {
      default: 2
      min: 2
      max: 100
    }
  }
  
  inputs.each do |input|
    input.name = ""
  end
  
  def run
    if all the inputs are the same
      output.value = true
    else
      output.value = false
    end
  end
end
```
Nodes are non-visual. To display they are extended with visual aspects.
Visual aspects include.

Icon, Position?

```cr
{
  name: "Not Gate"
  icon: "not.png"
  desc: "Reverse input"
}
```

```cr
{
  name: "Not Gate"
  icon: "not.png"
  desc: "Reverses input"
  # --- #
  inputs: {
    amount: 1
    names {
      0: "input"
    }
  }
  outputs: {
    amount: 1
    names {
      0: "output"
    }
  }
  action: {
    outputs: {
      0: reverse(inputs[0])
    }
  }
}
```

```cr
NOT:
  name: "Not Gate"
  icon: "not.png"
  desc: "Reverses input"
  inputs:
    0: "input"
  outputs:
    0: "output"
  actions:
    outputs:
      0: reverse(inputs[0])
      
AND:
  name: "And Gate"
  icon: "and.png"
  desc: "Activated when both inputs are active."
  inputs:
    0..1(i): "input #{i}"
  outputs:
    0: "output"
  actions:
    outputs:
      0: if(inputs.uniq.size === 1).to_perc
      
COUNTER:
  name: "Counter"
  icon:
    fill(counter / max, #fff)
  desc: "Count up until active"
  inputs:
    0: "Count up"
    1: "Reset"
  outputs:
    0: "Output"
  actions
    properties:
      counter: 0
      max: 10
      min: 0
    inputs:
      0: counter += 1
      1: counter = min
    outputs:
      0: (counter / max)
    
```cr
NOT > SAY("Hello World!")
# => "Hello World!"
```
https://i.imgur.com/MfN4sgq.png

I can't think of how it would worka



