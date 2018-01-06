# Brief About Ruby
## Inception  
- Written by "Yukihiro Matsumoto" (Matz) in 1995.
- Matz blended parts of his favorite languages like Perl, Smalltalk, Eiffel, Ada, and Lisp.
- Matz say's "Ruby is simple in appearance, but is very complex inside, just like our human body"

## Pure Object-Oriented
```ruby
# Everthing is object in Ruby.
5.times{ print "We are learning Ruby!!!\n" }
```
## Flexibility
+ Allows its users to freely alter its parts. 
+ Essential parts of Ruby can be removed or redefined. 
+ Existing parts can be added upon. 
+ Ruby tries not to restrict the coder.
```ruby
class Integer
  def plus(x)
    self + x
  end
end
p 5.plus(6)
=> 11
```
## Blocks: a Truly Expressive Feature
+ A programmer can attach a closure to any method, describing how that method should act.
+ The closure is called a _block_
+ Blocks are inspired by functional languages
+ Block is described inside the `do ... end` construct
```ruby
languages = ['C', 'Java', 'Ruby'].map do |lang|
  "I know #{lang}"
end
=> ["I know C", "I know Java", "I know Ruby"]
```
## Modules and Mixins
+ Modules are collections of methods.
+ Classes can mixin a module and receive all its methods.
```ruby
class Car
  include Mechanics
end
```  