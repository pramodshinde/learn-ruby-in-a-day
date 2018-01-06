# Modules and Mixins 
- Module is set of methods
- Similar to interfaces in Java
- Modules can be included or extended to mix-in into classes 

## Syntax 
```ruby
module ModuleName
#code
end
``` 
## Example
```ruby
module Cleanable
  def clean
    p "In clean #{self}"
  end
end

module Saleable
  def sale
    p "In sale #{self.class}"
  end
end
```
### Including module 
- Module methods are available as instance methods on include
```ruby
class Car
  include Saleable
end

Car.new.sale
#=> "In sale Car"
```
### Extending module 
- Module methods are available as instance methods on extend
```ruby
class Car
  include Saleable
  extend Cleanable
end

Car.new.sale
Car.clean
#=> "In clean Car"
#=> "In sale Car"
```

## Assignment: 
1. Can we extend and include module at the same time?
2. What happens if two modules have same method and both included in same class?
 