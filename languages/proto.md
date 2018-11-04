1 + 1
1(+(1))

typeof + // => Object > Char
typeof 1 // => Object > Number
typeof hi // Object > SpecialCollection<Char>
typeof "hi" // => Object > String

// works by creating three
+ + +

// works by adding three
1 + + +

// psuedocode for how this works
// the current "last = #last |= 0" could be changed
obj '+' do
  act Char do
    return `~{#last.chr} + ~{#last.chr}`
  end

  act Number(last = #last |= 0, next = #next |= 1) do
    return `~{last} + ~{next}`
  end
end

+ +
+(+)

// is 1 because 0 + 1 = 1
+ # => 1

// is 2 because (0 + 1) + 1 = 2
+ + # => 2

// is 11 because
// #last = 5
// #next = 6
// think of it like
// (5)+(6) instead of
//  5.+(6)
// 5 + 6 = 11
5 + 6
