# Data Types In Ruby
## Numbers 
### Integer (Fixnum and Bignum)
```ruby
90000  #Is a integer
90_000 #Is also integer, '_' used for readability 
```
- In Ruby < 2.4.0 
```ruby
p 9_000_000.class
=> Fixmun
p 9_000_000_000_000_000_000_0.class
=> Bignum
```
- In Ruby >= 2.4.0 
```ruby
p 9_000_000.class
p 9_000_000_000_000_000_000_0.class
=> Integer
``` 
### Float
```ruby
p 12.5.class #=> Float
p -12.5.class #=> Float
p (5.0 / 2).class #=> Float
```
### Symbols
- Begins with ':'
- Often used in hashes as keys 
```ruby
p :my_name
=> :my_name
switch = :on
p switch
=> :on
```
### Strings
```ruby
p "Ruby" #=> Ruby
p "Ruby".size #=> 4
p "Ruby".upcase #=> "RUBY"
p "Ruby".reverse #=> "ybuR"
p 23.to_s #=> "23"
p 'ruby'.to_sym #=> :ruby
"Learning Ruby is Fun".split(" ")
#=> ["Learning", "Ruby", "is", "Fun"]
```
### Hash
- Declaring a hash 
```ruby
# Using symbols as keys 
student = {  first_name: 'Ruby', last_name: 'Lover' } 

# Using Symbols and Hash Rocket (=>)
student  = {  :first_name => 'Ruby', :last_name => 'Lover' }

# Accessing elements
student[:first_name]  #=> 'Ruby' 

# Using String and Hash Rocket (=>)
student = {  "first_name" => 'Ruby', "last_name" => 'Lover' }
# Accessing elements
student['first_name']  #=> 'Ruby'
```
- keys, values and each method
```ruby
student.keys
 => [:first_name, :last_name]
student.values
 => ["Ruby", "Lover"]
student.each do |key, value|
  p key, value
end
#=> :first_name
#=> "Ruby"
#=> :last_name
#=> "Lover"
```
### Array
- Declaring an Array
```ruby
nums = [1, 2, 3, 4]
puts nums.size
#=> 4
nums.each do |num|
  puts num
end
#=> 1
#=> 2
#=> 3
#=> 4
```
- Array with `new` method
```ruby
Array.new      #=> []
Array.new(3) #=> [nil, nil, nil]
Array.new(3, true) #=> [true, true, true]
```
- Some methods of array
```ruby
nums.max
#=> 4
nums.reverse
#=> [4, 3, 2, 1]
nums.last
#=> 4
nums.first
#=> 1
["Learning", "Ruby", "is", "Fun"].shuffle.join(' ')
#=> "is Fun Ruby Learning"
["Learning", "Ruby", "is", "Fun"].shuffle.join(' ')
#=> "Learning is Fun Ruby"
["Learning", "Ruby", "is", "Fun"].shuffle.join(' ')
#=> "Ruby Fun Learning is"
```