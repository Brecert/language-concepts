## Uniform
```py
def add(one, two):
  return one + two

x = "Hello World!"
print(x)
```

```
a1 = Arg("one", :none)
a2 = Arg("two", :none)
r1 = Return(Variable("one"), Call("+"), Variable("two"))
e1 = ExpressionList(r1)
b1 = Block(e1)
Call("add", a1, a2, b1)
```
