# Progrmming in Ruby

## Table of Contents

- [Progrmming in Ruby](#progrmming-in-ruby)
  - [Table of Contents](#table-of-contents)
  - [Data Types and Bulit-In Methods](#data-types-and-bulit-in-methods)
    - [Numbers](#numbers)
    - [Strings](#strings)
    - [Arrays](#arrays)

## Data Types and Bulit-In Methods

Ruby has most standard data types with lots of built-in methods. There are ofthen multiple methods to achieeve the same goal in a slightly different way.

### Numbers

Numbers in Ruby are either int or float. All standard mathematical opperations are possible.

### Strings

- Interpolation: `"#{}"`
- Concatenation: `"Sun" + "shine"` = "Sunshine"
- Methods
  - `String.capitalize` - Makes the first letter of every word capitalized, the rest lowercase.
  - `String.downcase` - Makes all letters lowercase
  - `String.upcase` - Converts string to all caps
  - `String.concat(other_string)` - Concatenates strings
  - `String.slice(starting_index, ending_index_plus_one)` - Cut out part of a string
  - `String.gsub(to_replace, replacement)` - Replaces one character sequence with another
  - `String.replace(replacement)` - Replace the entire string with another
  - `String.include?(search)` - Boolean whether or not the string contins the search
  - `String.length` - Returns the character count of the string (including spaces)
  - `String.chomp` - Removes leading and ending whitespace and `\n`
  - `String.strip` - Remove leading and trailing white space
  - `String.to_f` - Converts string to a float
  - `String.to_i` - Converts string to an int

### Arrays

- Standard construction [].
- Use the shovel operator >> to add elements to the end of an array
- Basic methods
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
  - `Array.select` - Returns an array the same size **or smaller** where the elements meet a given condition.
  - 