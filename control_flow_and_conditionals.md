# Control Flow and Conditionals 
## If..else statement 
### Syntax
```ruby
if conditional [then]
   code...
[elsif conditional [then]
   code...]...
[else
   code...]
end
```
### Example
```ruby
number = 10
if number.between?(1,20)
  p 'Number is between 1 to 20'
else
  p 'Number is not between 1 to 20'
end
#=> 'Number is between 1 to 20'
```
## If modifier 
### Syntax
```ruby
code if condition 
```
### Example
```ruby
p 'Number is between 1 to 20' if number.between?(1,20)
#=> 'Number is between 1 to 20'
```
## unless..else statement 
### Syntax
```ruby
unless conditional [then]
   code
[else
   code ]
end
```
### Example
```ruby
number = 10
unless number.between?(1,20)
  p 'Number is between 1 to 20'
else
  p 'Number is not between 1 to 20'
end
#=> 'Number is not between 1 to 20'
```
## unless modifier
### Syntax
```ruby
code unless condition 
```
### Example
```ruby
p 'Number is not between 1 to 20' unless number.between?(11,20)
#=> 'Number is not between 1 to 20'
```
## case statement 
### Syntax
```ruby
case expression
[when expression [, expression ...] [then]
   code ]...
[else
   code ]
end
```
### Example
```ruby
lang = ['Ruby', 'Java', 'C', 'Python'].sample
case lang
when 'C'
  p "#{lang} is awesome!"
when 'Java'
  p "#{lang} is awesome!"
when 'Python'
  p "#{lang} is awesome!"
else
  p "#{lang} is more awesome!"
end
#=> "Ruby is more awesome!"
```
