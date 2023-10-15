# RegEx Tutorial: Matching a URL

The following tutorial will breakdown a regular expression that is used for matching and verifying URLs. A regular expression or regex, is a series of characters that define a search pattern. They allow you to describe, match, or parse through text. With this URL matching regex we will verify a url matches a certain format.

## Summary

```/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/```
The regex above is used for matching and verifying URLs. I will be breaking down the various regex components such as the anchors, quantifiers, OR operators, character classes, and flags in this expression.


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
Between the two ways to create a regex object, literal notation and constructor function notation, the Matching URL regex uses literal notation- meaning the pattern is wrapped in slashes (/). 


### Anchors
The anchors in this expression are the "^" character at the beginning of the expression and the "$" character at the end of the expression. The "^" character asserts position at the beginning of the string. The "$" character asserts position at the end of the string and right before the "/" line terminator. 

### Quantifiers
```/^(https?:\/\/)?([\da-z\.-]+)\.([a-z\.]{2,6})([\/\w \.-]*)*\/?$/```
Quantifiers in regular expressions are numbers of characters or expressions that need to be matched. The first quantifier in this regex is the "?" that immediately follows the text "https" and then follows the ")" The "?" quantifier allows the preceding characters (https) to show up once or zero times- which means that ths url can have either one protocol (http(s)) or none at all. This quantifier wraps the first capturing group of the regex meaning the characters in that first set of parentheses can be used once or zero times. This is also used at the very end of the expression and refers to a "/" being an option to use once or not at all at the end of the URL.

The following quantifier used is the "+" at the end of the second capturing group. The second capturing group is the main domain part of the url- this group is saying that there can contain lower case letters (a-z), digits (\d), dots (.), and hyphens (-). 


The next quantifier is the "{2,6}". This quantifier is representing the TLD portion of a URL (.com, .io, .net for example) and says that this portion should be between 2 and 6 characters long. 

Finally, the last quantifier that is used in the URL matching regex is the asterisks towards the end of the exression. This asterisk means that the group can appear 0 or more times. This final section is saying that the url can have zero or more paths. 


### OR Operator

### Character Classes

### Flags

### Grouping and Capturing

### Bracket Expressions

### Greedy and Lazy Match

### Boundaries

### Back-references

### Look-ahead and Look-behind

## Author

A short section about the author with a link to the author's GitHub profile (replace with your information and a link to your profile)

