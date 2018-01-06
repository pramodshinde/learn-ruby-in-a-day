# Loops 
## while statement 
### Syntax
```ruby
while conditional [do]
   code
end
```
### Example
```ruby
number = 0
while number < 3 do
  p "#{number} is < 3"
  number += 1
end
#"0 is < 3"
#"1 is < 3"
#"2 is < 3"
```
## while modifier
### Syntax
```ruby
code while conditional
or
begin 
 code
end while conditional
```
### Example
```ruby 
begin
  p "#{number} is < 3"
  number += 1
end while number < 3
#"0 is < 3"
#"1 is < 3"
#"2 is < 3"
```
## for statement 
### Syntax
```ruby
for variable [, variable ...] in expression [do]
   code
end
```
### Example 
```ruby
for i in 0..2
   puts "Value of local variable is #{i}"
end
#=> Value of local variable is 0
#=> Value of local variable is 1
#=> Value of local variable is 2
```
## Assignment: 
1. Explore `until` loop in Ruby.
2. Find out how to use `break`, `next`, `redo` and `retry`
