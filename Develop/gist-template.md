# Title (Regex No Rejects- Tutorial: Regex Matching a Hex Value)

Regular expressions are patterns used to match character combinations in strings. In a regular expression the metacharacter ^ means "not". So, while "a" means "match lowercase a", "^a" means "do not match lowercase a".

## Summary

Hex value can be used for color value. An example of this would be red is define as #FF0000, green as #00FF00, black as #000000 and as you can tell each Hex Value is composed of the number sign or also known as pound sign # follow by a set of six digit 0-9 and letter characters a-f. Subsequently, some hex value would also just be the number sign followed by three digit or letter characters a-f, such as the color black #000000 and #000 are the same.

## Table of Contents
- [Regex Components](#regex-components)
- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)


## Regex Components

Regex is considered a literal, meaning the pattern must be define inside slash characters / such as our Hex Value example: /^#?([a-f0-9]{6}|[a-f0-9]{3})$/

### Anchors

^ and $ are both considered anchors.

^ Matches the starting point within the string. $ Matches the ending point of the string.

Which mean for our Hex Value, we will start looking for the # symbol and end with any character between a-f or number 0-9. This is the simple idea of it but will go in more details on what other parameters there is to define what to really look for.

### Quantifiers

? and {} are quantifiers

? states that the expression must match once or none. {} sets limits for a match

in our example hex value regex /^#?([a-f0-9]{6}|[a-f0-9]{3})$/ the {6} or {3} states that it must match exactly the number inside of the curly brakets which would be 6 or 3 characters, that are defines before the curly brackets.

### OR Operator

The OR operator symbol is | and is used to define an expression to look for a specific character or sets of characters. For our Hex value example, /^#?([a-f0-9]{6}|[a-f0-9]{3})$/ , we are looking for either [a-f0-9]{6} or [a-f0-9]{3} sets of characters.

### Character Classes

A character class in a regex defines a set of characters, any one of which can occur in an input string to fulfill a match. Character classes are used to search specific expressions. 

IE. When searching for any numeric digit we could define the search as \d which means search for any digit. A good example would be searching for phone numbers. You use the following to conduct a search for 9 digit phone numbers. \d\d\d-\d\d\d-\d\d\d\d


Character class are case sensitive and perform inverse search. Meaning \d will search for any digit while \D will search for any non-digit characters.

### Flags

Regular expressions may have flags that affect your search. A regex must be wrapped inside slashes, the only exception to this rule is flag components. The flag will be placed outside of the slash at the end of the regex. There are six different flags with their own sets of function to affect the regex.

i - with this flag the search is case-insensitive, meaning there is no difference between A and a
g - search for all matches, without it this flag it will only return the first match
m - multiline mode
s - enable "doall" mode which allows a dot . to match newline character \n
u - enable full Unicode support
y - "sticky" mode which search the exact position in the text

### Bracket Expressions

Inside of the square brackets [] represents the range or characters to match in an expression. The character inside the brackets does not mean that the search will be an exact match but instead it will return any string that countain that character.
IE: This is a test the search for [s] will return the words "This is test" as they all have the character s in it. Using the same text example but defining the search to include any letter between o-t as [o-t], which is define by using the hyphen symbol -, the search will still be returning "This is test" as the only word without any letter from o to t is the "a" word. If we were to define the search as [a-i] this time it will return everyting as each word does include a letter that is between a-i. Note that a-z and A-Z are considered different as lowercase and uppercase are not define as the same. If we wanted a search to include both lowercase and uppercase it would had to be define as such [a-zA-Z] which by virtue of our regex /^#?([a-f0-9]{6}|[a-f0-9]{3})$ we will not be looking for any uppercase value. A better regex should actually be /^#?([a-fA-F0-9]{6}|[a-fA-F0-9]{3})$ as some people like to have these letter character in uppercase.

### Greedy and Lazy Match

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/
A greedy match tries to match an element as many times as possible. Whereas, a lazy match tries to match an element as few times as possible. In our example we have ? which signifies lazy quantifier. This is referred to a lazy quantifier because it causes the regular expression engine to match as few occurances as possible. We can simply turn this lazy match into a greedy one by adding a ?.

## Author

https://github.com/AaronPearson1. 
