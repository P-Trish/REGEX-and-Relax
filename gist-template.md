# REGEX and Relax: A Tutorial Gist On Matching An Email 

A regular expression, or regex is a sequence of characters that defines a specific search pattern.  It can be used to find certain patters of characters within a string, in this case an email.  

This tutorial demonstarates how a regex functions by breaking down each part of an email expression and describing what it does.  



## Summary

In this gist, I provide a tutorial of how the regex ```/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/``` is used to match an email value and how each component works.

The different parts of the above email regex have specific roles in ensuring that a user inputs an email address that starts with an undetermined amount of characters before the @ symbol and ends with a domain name.



## Table of Contents

- [Anchors](#anchors)
- [Quantifiers](#quantifiers)
- [Grouping Constructs](#grouping-constructs)
- [Bracket Expressions](#bracket-expressions)
- [Character Classes](#character-classes)
- [The OR Operator](#the-or-operator)
- [Flags](#flags)
- [Character Escapes](#character-escapes)



## Regex Components

The regex ```/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/``` is used to match an email value.  



### Anchors `^`  `$`
The anchors used in regex for matching an email are `^` which represnts the start of the string, and `$` which represents the end of the string.  

These two anchors together make sure that the regular expression only matches strings that start with the given pattern and end with the given pattern.



### Quantifiers `+` `{}`

The first quantifier in this email regex is `+` which represents the quantifier "one or more" as there are a specified amount of characters before and after the `@`, and before the `.` that leads to the domain name . This operator connects the users email + email service + domain name.  In addition, the `{2,6}` quantifier sets the amount minimum and maximum characters range (2-6) for the character set of the domain name as seen in this code snippet: ([a-z\.]{2,6})$/




### Grouping Constructs `()`

```()``` represents a capturing group. It means that whatever is matched inside the parentheses will be captured as a separate group.

The grouping constructs in this email regex are:

- ([a-z0-9_\.-]+) this capturing group matches the user email name.
- ([\da-z\.-]+) this capturing group matches the email service.  
- ([a-z\.]{2,6}) this capturing group matches the domain name.  



### Bracket Expressions `[]`

```[]``` represents a bracket expression. It means that any character inside the brackets can match the corresponding character in the input string.
The bracket expressions in this email regex are:
- [a-z0-9_\.-] which matches any lowercase letter "a-z", "0-9", "_" (underscore), "-" (hyphen), and "." (dot), in the user email name.
- [\da-z\.-] which matches single character that is either a digit (/d), a lowercase (a-z), a ".", or "-". Here, the backslash before the d (\d) is an escape character used to match any digit from 0 to 9 in the email service.
- [a-z\.] which matchaes any lowercase character "a-z", and a ".", in the domain name. 




### Character Classes `\d` `\w`

- \d represents a single digit character class. It is equivalent to [0-9]. It will only match a single digit such as "0" not "00."
- \w represents a word character class. It is equivalent to [a-zA-Z0-9_].



### The OR Operator

`|` represents the OR operator. It means that either the expression on the left or the right can be matched such as in the three grouping constructs of an email.  



### Flags `/` 

There are no flags used in this email regex, however because it is considered a literal, it must be wrapped in slashes. Flags would be placed after the second slash at the end of the regex to define additional functionality or limits.  



### Character Escapes `\.`

\. represents a literal dot character. It is escaped with a backslash because the dot has a special meaning in regular expressions.
In regular expressions, the dot (.) inside the square brackets is treated as a literal character because it loses its special meaning when used inside a character class.



## Author

Patricia Alberto is a full-stack bootcamp student ready to apply her new skills and become a full-stack web developer.  Check out her works here: https://github.com/P-Trish 
