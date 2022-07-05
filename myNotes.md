# Attribute Accessor Macros

## Learning Goals
-Define what a 'macro' is 
-Use macros to abstract away the explicitly defined setter and getter methods in a Ruby class

## What is a Macro?
- similar to a method; instead of returning a Ruby datatype, a macro returns more code. 

- we will learn how to use macros to write the definitions of other methods

## Attribute Readers and Writers

```rb
class Person

  attr_reader :name
  # def name
  #   @name
  # end

  attr_writer :name
  # def name=(value)
  #   @name = value
  # end

end
```
The **attr_reader** macro, followed by the attribute name `:name`, _created a getter method_.

The **attr_writer** macro, followed by the attribute name `:name`, _created a setter method_.

These two methods effectively **write Ruby code** within our classes!

**Note:** What we're actually doing in each of those two lines of code is:

_calling the `attr_reader` and `attr_writer` methods_ and passing in the symbol
`:name` as an argument. 

Recall that in Ruby, calling methods works with or
without parentheses, so `attr_reader :name` is the same as `attr_reader(:name)`.

## Attribute Accessors
if we need BOTH getter and setter method for an attribute on our Person class, we can use another macro called, **Attribute Accessor**

So this code...

```ruby
class Person
    attr_writer :name
    attr_reader :name
end
```
...can now be written like this:

```ruby
class Person
  attr_accessor :name

end
```


