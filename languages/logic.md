```cr
Node
  inputs  : Int
  outputs : Int
end
  
Not < Node
  inputs : 1
  outputs: 1
end
  
  def run
    for input in inputs do |index|
      output[index]  = !input.value
    end
  end
  
