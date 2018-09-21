
expression
  : '(' word *arguments ')'
  
arguments 
  : word | expression
 
word
  : "def!"
    {{ @defs += name }}
  | \w+
  
(def:
