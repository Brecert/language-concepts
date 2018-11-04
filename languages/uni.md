`[0-9]+`
Number
| value
| kind

`'\'' \S '\''`
Char
| value

`'[' elements ']' "of" kind`
List
| elements
| kind

`\w\S*`
Var
| name

