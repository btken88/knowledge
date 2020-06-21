# Programming in Ruby

## Table of Contents

- [Programming in Ruby](#programming-in-ruby)
  - [Table of Contents](#table-of-contents)
  - [Data Types and Bulit-In Methods](#data-types-and-bulit-in-methods)
    - [Numbers](#numbers)
    - [Strings](#strings)
    - [Arrays](#arrays)
    - [Booleans](#booleans)
    - [Hashes](#hashes)
  - [Methods](#methods)
  - [Classes and Objects](#classes-and-objects)

## Data Types and Bulit-In Methods

Ruby has most standard data types with lots of built-in methods. There are ofthen multiple methods to achieeve the same goal in a slightly different way.

### Numbers

Numbers in Ruby are either int or float. All standard mathematical opperations are possible.

### Strings

- Interpolation: `"#{}"`
- Concatenation: `"Sun" + "shine"` = "Sunshine"
- Common Methods
  - `String.capitalize` - Makes the first letter of every word capitalized, the rest lowercase.
  - `String.downcase` - Makes all letters lowercase
  - `String.upcase` - Converts string to all caps
  - `String.concat other_string` - Concatenates strings
  - `String.slice starting_index, ending_index_plus_one` - Cut out part of a string
  - `String.gsub to_replace, replacement` - Replaces one character sequence with another
  - `String.replace replacement` - Replace the entire string with another
  - `String.include? search` - Boolean if the string contins the search
  - `String.length` - Returns the character count of the string (including spaces)
  - `String.chomp` - Removes leading and ending whitespace and `\n`
  - `String.strip` - Remove leading and trailing white space
  - `String.to_f` - Converts string to a float
  - `String.to_i` - Converts string to an int

### Arrays

- Standard construction [].
- Use the shovel operator >> to add elements to the end of an array
- Common basic methods
  - `Array.push` - Add to the end of an array
  - `Array.pop` - Remove from the end of an aray
  - `Array.shift` - Add to the start of the array
  - `Array.unshift` - Remove from the end of the array
  - `Array.first` - Returns the first element in the array
  - `Array.last` - Returns the last element in the array
  - `Array.length/.count/.size` - Returns the number of elements in the array
- Enumerables/Loop methods
  - `for __ in __ do ... end` - Do something a certain number of times
  - `Array.each` - Do an opperation on each element of the array
  - `Array.map` - Returns an array of the same size with every element altered somehow
    - You can use the proc shorthand to simplify the map function since we use it so much
    - `Array.map(&:method)`
  - `Array.select` - Returns an array the same size **or smaller** where the elements meet a given condition.
  - `Array.find condition` - Returns the first element to meet a given condition
  - `Array.reduce` - Performs some operation on the array and returns one object which can be any data type
- Common Advanced methods
  - `Array.flatten` - Makes any nested arrays into part of the parent array
  - `Array.include? condition` - Returns a boolean if any element meets a given condition
  - `Array.join` - Combines all elements into a string in their index order
  - `Array.max` - Returns the maximum value in the array
  - `Array.min` - Returns the minimum value in the array
  - `Array.sample` - Returns a random element from the array
  - `Array.shuffle` - Randomly scrambles array elements
  - `Array.slice starting_index ending_index_plus_one` - Returns a section of the array
  - `Array.sort` - Sorts elements as indicated in the code block
  - `Array.sum` - Returns the sum of all elements
  - `Array.uniq` - Returns the array with duplicate elements removed

### Booleans

- Truthy - everything that exists
- Falsey - `nil` and `false`

### Hashes

Hashes are Ruby's way of storing key-value pairs

- There are multiple ways to set up key-value pairs:
  - {key: value} => key symbol
  - {:key => value} => key symbol
  - {"key" => value} => key string
- Accessing information by key:
  - `hash[:key]` - references symbol keys
  - `hash["key"]` - references string keys
- `hash["key"/:key] = value` - creates a new key-value pair
- Enumerables
  - `Hash.each` - Implicitly returns the original hash. Do something to/with each key-value pair
  - `Hash.select` - New hash with all truthy elements
- Common Methods
  - `Hash.compact` - Returns a new hash with all nil key-values removed
  - `Hash.default` - Shows or sets what will return when looking up a non-existent key
  - `Hash.empty?` - Boolean if the hash has any content
  - `Hash.has_key? search` - Boolean if the searched for key exists
  - `Hash.key? search` - Boolean if the searched for key exists
  - `Hash.include? search` - Boolean if the searched for key exists
  - `Hash.has_value? search` - Boolean if the search for value exists
  - `Hash.value? value` - Boolean if the searched for value exists
  - `Hash.inspect` - Returns the hash as a string
  - `Hash.key value` - Returns the key of a searched for value
  - `Hash.keys` - Returns an array of all keys
  - `Hash.values` - Returns an array of all values
  - `Hash.merge other_hash` - Combines two hashes. Second hash will override values for keys present in both. You can perform an operation by providing a block of code

## Methods

- Methods in ruby are defined with `def name_of_function parameter_list ........ end`
- Method names are snake_case
- Ruby implicitly returns the last line of a method
- Methods must be defined before they are called. You can 
- Changing built in methods is known as Monkey Patching

## Classes and Objects

- Classes are the blueprints used to create objects
- Objects are individual and distinct instances of a class
- `@variable` - instance variable available inside the object instance
- `@@variable` - class variable available inside all objects
- `self` - refers to that instance **or class** depending on scope
- `attr_reader` - macro to create getter methods for `:instance_variables`
- `attr_writer` - macro to create setter methods for `:instance_variables`
- `attr_accessor` - macro to create setter and getter methods for `:instance_variables`
- `@@all = []` - class variable used to store all instances of a class
- Always initialize all properties
- If chaining instance methods, make sure you have the method return self
- Standard setup of a class:
  
```ruby
class SomeClass
  attr_reader :some_variable
  attr_writer :some_other_variable
  attr_accessor :yet_another_variable

  @@all = []

  CLASS_CONSTANT = value_available_in_all_instances

  def initialize required_initialization_parameters
    @some_variable = variable_from_parameters
    @some_other_variable = variable_from_parameters
    @yet_another_variable = variable_from_parameters
    self >> @@all
  end

  def self.all
    @@all
  end

  def some_variable
    @some_variable
  end

  def some_other_variable=input
    @some_other_variable = input
  end

  def instance_method
    do_something
  end

  def self.class_method
    do_something
  end
end
```
