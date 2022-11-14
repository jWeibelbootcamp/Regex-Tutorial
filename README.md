# Regex-Email-Tutorial

Plain Text explanation of an email match Regular Expression to understand it's search pattern. 

## Summary

The following Regular Expression (Regex) searches for characters matching a specific email format: `/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`. (Add brief description of full functionality)

## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [OR Operator](#or-operator)
- [Character Classes](#character-classes)
- [Flags](#flags)
- [Grouping and Capturing](#grouping-and-capturing)
- [Bracket Expressions](#bracket-expressions)
- [Greedy and Lazy Match](#greedy-and-lazy-match)
- [Boundaries](#boundaries)
- [Back-references](#back-references)
- [Look-ahead and Look-behind](#look-ahead-and-look-behind)

## Regex Components

### Anchors
  The `^` and `$` characters are the beginning and ending anchors of the expression, wrapped in `/` characters.  The `^` and `$` characters indicate that the characters following and preceding them, respectively, are the characters which must be matched.  These can take the form or an exact string or a bracketed range of possibilities. This email match regex uses the latter.
  
### Quantifiers
  The `*`, `+`, and `?` characters are quantifiers - setting limitations to the regex sections to which they are attached. The `*` character matches the pattern a minimum of zero times.  The `+` character matches the pattern a minimum of one time. The `?` character matches the pattern a maximum of one time. Curly braces `{ }` can provide additional limitations by matching exactly `{ n }` times, at least `{ n, }` times, or within a range of `{ n, x}`. 
  
  Our regex contains three sets of parenthesis: `([a-z0-9_\.-]+)`, `([\da-z\.-]+)`, and `([a-z\.]{2,6})`. The first two end with `+` characters, requiring a minimum of one matching character in the set.  The last one has a min-max required range of `{2,6}`.

### OR Operator
  The OR operator `|` allows for matching less than all of the characters in a set of parenthesis, e.g. `(a|b|c)`. Bracketed expressions naturally function as OR expressions, allowing anything, not necessarily everything, within the range to satisfy the search. 
  
  Our regex makes use of three bracketed expressions: `[a-z0-9_\.-]`, `[\da-z\.-]`, and `[a-z\.]`.  As such, it does not require an OR operator. 

### Character Classes
  Classes define a set of characters from which a match can occur. The `.` character includes all characters except the newline character `\n`. The `\w` character matches any alphanumeric character. The `\d` character matches any numeral digit. The `\s` character matches any whitespace character. All but the `.` can be changed to exclude instead of include their characterset by capitalizing the letter, e.g. `\N`. 
  
  Our regex makes use of bracketed expressions, also considered character classes, to determine its character searches, and does not contain any non-bracketed classes.

### Flags
  In order to prevent a regex from being read as a literal, it must be wrapped in `/ /`. Flags are an exception to this rule and are placed outside of the second `/` at the end of the regex.  There are seven total flags, each adding an additional parameter to the search. `d` generates indices for substring matches. `g` indicates a global search. `i` removes case sensitivity. `m` allows newline characters to be matched by anchors. `s` allows the `.` character to match newline characters. `u` treats a pattern as unicode. `y` makes a search "sticky," starting at the current point in the target string. 
  
  Our regex does not use flags. 
  
### Grouping and Capturing
  Grouping is mainly accomplished through parenthesis, creating subexpressions within the expression. Subexpressions, as opposed to bracket expressions, look for exact matches. A capturing group captures the matched characters for later reference. 

### Bracket Expressions
  Any set of characters inside a set of square brackets `[ ]` is treated as a character class including non-required, but acceptable match characters. A range of alphnumeric characters can be represented by a range with a hyphen, e.g. `[a-z]` or `[0-9]`. The underscore `_` and hyphen `-` are also commonly included. A common bracket expression puts all of these together: `[a-z0-9_-]` and will match any string containing any combination of lowercase letters, numbers 0-9, an underscore, or a hyphen. 
  
  A bracket expression can also be inverted to exclude its contents by adding the `^` character at the beginning, e.g. `[^a-z]`. 
  
   Our regex makes use of three bracketed expressions: `[a-z0-9_\.-]` - matching any alphanumeric character a-z, 0-9 as well as `_`, `.`, `-`, `[\da-z\.-]` - written differently, but matching the same minus the `_`, and `[a-z\.]` - matching letters a-z and `.`.

### Greedy and Lazy Match
  Matches are greedy - match as many occurences as possible - unless otherwise limited. The `?` character makes a match lazy - matching as few occurences as possible. Our regex does not use lazy matching. 

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)