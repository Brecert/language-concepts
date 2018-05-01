```cr
true = 100
false = 0

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


