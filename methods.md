# Methods, Arguments and Kewargs In Ruby.
### Syntax
```ruby
def method_name(argument1, argument2...)
end
```
### Example
```ruby
def square(x)
  x**2
end
square(3) #=> 9
square 8 #=> 64
```
### Default argument
```ruby 
def power(x, pow=2)
  x**pow
end
power(2) #=> 4
power(2, 3) #=> 8
```
### Return values
- By default `return` value of method is value of last execution statment
```ruby
def power(x, pow=2)
  return 'invalid' if pow < 0 
  x**pow
end
power(2, -1) #=> 'Invalid'
```  
## kewargs 
- Also called as Keyword argument 
```ruby
def power(number:, pow:)
   number**pow
end
power
#=> ArgumentError: missing keywords: number, pow
power(number: 8, pow: 3)
#=> 512
power(pow: 3, number: 8)
 => 512
```

### Assignment 
1. Find out more differences between arguments and keyword arguments
2. How to pass default keyword arguments
3. How to return multiple values from methods