# How to use Markdown
_This files shows you how to use the basics of Markdown_

This is more of a cheat sheet. For a better guide, please go to the [GitHub Markdown Guide](https://guides.github.com/features/mastering-markdown/).

## Section 1: Using Headers

### Types of Headers
  You use the hash marks to denote headers. 
  One hashtag/pound signs is equivalent to an html `<h1>` tag. 
  Two would be equal to an `<h2>` tag, etc.
 
 ## Section 2: Lists
 
 Lists are **super** easy in Markdown.
 
 An unordered list is simply a dash or an asterisk before each item.
 - Top of the list
 - Second item
 - Last item
  * I can change it up with an indent
  * And just keep adding more content

Ordered lists are also easy.
  1. Tab, Number, Period.
  2. It's that easy.
  3. What if you want to add a sub list?
    1. Tab and start numbering again.
      - You can combine list types
      - And keep outlining as you like.
      
## Section 3: Fun Stuff

> Use the alligator brackets to denote a block quote.
> This can be useful when quoting large sections of something else.

*However* for code, you should really use inline or block code.

### Example 1
 `inlineCode(example)`

### Example 2
  ```Python
  
  def main():
    blockCode()
    
    
  def blockCode():
    for i in range(10):
      print("Define your code type before you start your code sample")
      print("Make sure to encase your code with three ```")
  
  main()
  ```
  
  
