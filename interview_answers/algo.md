Given the word list:

```
word_list = [ "hello", "helicopter", "shaving", "door", "aluminum", "pen" ]
```
1. Write a function that prints out the longest word and its length, the shortest word and its length, and the average word length

```ruby
word_list = [ "hello", "helicopter", "shaving", "door", "aluminum", "pen" ]
word_average = word_list.join.length.to_f / word_list.length # Add the total length / by # of items
word_list.sort! { |a, b| b.length <=> a.length }
puts "The longest word is #{word_list.first} and is #{word_list.first.length} letters long. The shortest is #{word_list.last} and is #{word_list.last.length} letters long. The average word length is #{word_average}!"
```
2. Reverse the letters of each word in the array and sort from shortest to longest.

```ruby
word_list.sort! { |a, b| a.length <=> b.length }.map(&:reverse!)
```
