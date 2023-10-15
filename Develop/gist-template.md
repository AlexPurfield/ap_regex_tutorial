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

The following quantifier used is the "+" at the end of the second capturing group. The second capturing group is the main domain part of the url- this group is saying that there can contain lower case letters (a-z), digits (\d), dots (\.), and hyphens (-). 


The next quantifier is the "{2,6}". This quantifier is representing the TLD portion of a URL (.com, .io, .net for example) and says that this portion should be between 2 and 6 characters long. 

Finally, the last quantifier that is used in the URL matching regex is the asterisks towards the end of the exression. This asterisk means that the group can appear 0 or more times. This final section is saying that the url can have zero or more paths. This third character class is in the fourth and final capturing group that matches a sequence of characters: [\/\w \.-]. The first part of the class, "\/" allows a forward slash, "\w" matches any character from the basic Latin alphabet including the underscore(a-z, A-Z, 0-9, _), "\." once again matching the dot character, and "-" allowing hyphens. This final group represents the paths that can go at the end of a url.



### OR Operator
This regex does not use any specific OR operator (|).

### Character Classes
There are two character classes used in this regular expression:

1) \w : matches any character from the basic Latin alphabet including the underscore(a-z, A-Z, 0-9, _)
2) \d : matches any number 0-9


### Flags
There are no flags in the URL Matching regular expression. 

### Grouping and Capturing
As mentioned in the above sections, there are four different capturing groups in this regular expression for matching a URL:
1) (https?:\/\/) - for the protocol section of a URL 
2) ([\da-z\.-]+) - for the domain section of a URL
3) ([a-z\.]{2,6}) - for the TLD section of a URL
4) ([\/\w \.-]*) - for the paths section of a URL
These capturing groups separates the regular expression into subpatterns that allow us to put quantifiers between the groups so different sections can have different quantifiers attached. 

### Bracket Expressions
There are two bracket expressions in this regex: one in the second capturing group, one in the third capturing group, and one in the fourth capturing group- they are recoginzable by the square brackets ([]). The first character class: [\da-z\.-] is describing the domain part of the URL. It breaks down to "\d" matching digits 0-9; "a-z" matching any lowercase letters a-z; allowing and matching dots "\."; and matching hyphens.

The second bracket expression is in the third capturing group is [a-z\.]. This expression is referring to the TLD of the URL (.com, .net, .io) and is matching lowercase letters a-z (a-z), and dots (\.). As stated in the quantifiers above, this is limited to 2-6 characters.

### Greedy and Lazy Match
All of the quantifiers in this regex are greedy by default. The difference in greedy and lazy match quantifiers is that greedy match matches as much as they can while still keeping in line with the matching rules. "*" and "?" are both greedy in this regex. 

### Boundaries
Boundary (\b) is not used specifically in this regular expression but it is anchored with "^" at the beginning of the string and "$" at the end. 

### Back-references
There are no back-references in this regex. 

### Look-ahead and Look-behind
There are no look-ahead or look-behind assertions in this regex.

### Resources
[https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Regular_expressions/Cheatsheet]


## Author

Alex Purfield: [https://github.com/AlexPurfield]

