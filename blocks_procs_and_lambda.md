# Blocks, Procs & Lamdas 
## Blocks
- Group of code enclosed between `do..end` to `{}`

### Syntax
```ruby
{ #code goes here }
#or using do..end
do
 #code
end
```
### Example without argument
```ruby
def my_method
  p 'in my method'
  yield
  p 'in my method'
end

my_method { p 'in block' }
#=> "in my method"
#=> "in block"
#=> "in my method"
``` 
### Example with arguments
- Passing argument to block 
```ruby
def my_name(name)
  p "Name in method: #{name}"
  yield(name.upcase)
end

my_name('pramod') { |up_case_name| p "Name in block: #{up_case_name}" }
#=> "Name in method: pramod"
#=> "Name in block: PRAMOD"
```
### Using `&block` argument
```ruby
def my_name(name, &block)
  p "Name in method: #{name}"
  block.call(name.upcase)
  yield(name.reverse)
  p "Again in method: #{name}"
end

my_name('pramod') { |name_in_block| p "Name in block: #{name_in_block}" }
#"Name in method: pramod"
#"Name in block: PRAMOD"
#"Name in block: domarp"
#"Again in method: pramod"
```
## Lambda and Proc
### creating lambda using `lambda` 
```ruby
my_lambda = lambda { [|arg1, arg2...|] code } 
or 
my_lambda = lambda do [|arg1, arg2...|]
#cod
end
```
### creating lambda using `->` 
```ruby
my_lambda = ->[(arg1, arg2...)] {  code } 
or 
my_lambda = ->[(arg1, arg2...)] do
#code
end
```
### Example
```ruby
lam = lambda { |num| num ** 2 }
p lam.call(4) # 16

lam = ->(num) { num ** 2 }
p lam.call(4) # 16
```
### Creating Proc
### Syntax
```ruby
my_proc = Proc.new { [|arg1, arg2...|] #code }
or 
my_proc = Proc.new do [|arg1, arg2...|]
#code
end
```
### Example
```ruby
proc = Proc.new { |num| num ** 2 }
p proc.call(4) # 16

### Passing Proc, Lambda to method
def my_method(proc)
  proc.call(4)
end
p my_method(proc) #16
p my_method(lam) #16
```

### Assignments
- Find out difference between Block, Lambda and Proc.
- Can we pass proc and lambda as keyword argument to method? 
