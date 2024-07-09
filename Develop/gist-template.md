# Regular Expressions: Matching an Email Address (replace with your title)

A Regex, or "Regular Expression", is a series of characters used to check whether or not a string meets the requirements for what it is trying to represent, such as a username or password. In this tutorial we have a regex that is being used to validate that an email address meets the necessary character requirements. 

## Summary

The regex I will be describing is one for matching an email address. I will break down the expression into parts and explain what the symbols/groups of symbols represent. \
Regex code snippet: Matching an Email – /^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

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
- [References](#references)

## Regex Components
/^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/

I will break down this expression into 3 parts.

1. The regex starts with an opening slash and an anchor: /^. The following criteria set forth is that the first part of the email (before the @) can be a character between a-z, number between 0-9, and can include an underscore, period, or a hyphen. This is represented by the following: ([a-z0-0_\.-]) where the [] includes the characters, and the () groups this set before the @ symbol, which is literal since we are talking about an email address. The + sign links the first part of the email to the second, which is followed by the @.

2. The next part of the expression is ([\da-z\.-]+) which is the part of the email address that usually includes the domain name. Here again we see the symbols inside of [] followed by a plus sign outside the brackets but within the parenthesis. This is connecting this group to the next part, which is separated by a period. In this group we see \d, which is the equivalent of saying [0-9]. So the breakdown of this expression would be that it can include a number between 0-9, lowercase letter a-z, a period, or a hyphen.

3. The final part of the expression is ([a-z\.]{2,6}) which is preceeded by \. which represents a literal period, and followed by $/ which is an anchor and a closing slash, respectively. In an email address, the domain is usually followed by 3 letters such as .com, but here we see there are other criteria that could also be fulfilled. It could be a lowercase letter between a-z and a period, and the numbers within the curly braces represent that this segment must be between 2-6 characters long.


### Anchors
Anchors are what begin and end the regex. Here these are represented by ^ at the start and $ at the end, inside of the forward slashes that wrap the entire expression.

### Quantifiers
Quantifiers are the numbers within the curly braces, separated by a comma. They denote that the string must be between a minimum and maximum number of characters.

### OR Operator
The OR operator is represented by | and used to show that an expression can include one thing or another. For example if we write (abc):(xyz) as (a|b|c):(x|y|z) it could include all three of the letters within the parenthesis or only one or two, in any order, as long as the abc part is before the colon and xyz after it. Without the OR operator, this expression would have to be written as abc:xyz in order to fit the criteria.

### Character Classes
Character Classes are a shorter way to define a set of characters. For example in the email address regex, we see \d which is used to represent [0-9]

### Flags
Flags are placed at the end of a regex, after the closing slash. They are used to represent additional functionality or limits for the regex. 

### Grouping and Capturing
Expressions can be grouped using parenthesis, and each pair of parenthesis is known as a subexpression. Each group can be capturing or non-capturing. Capturing groups capture the characters and can be potentially reused elsewhere in the expression, whereas non-capturing groups cannot be used again. A group can be made non-capturing by adding ?: at the beginning of an expression within the parentheses.

### Bracket Expressions
Bracket expressions can also be known as positive or negative character groups. A positive character group includes an expression that we want to match, while a negative character group are characters we do not want to match. Negative character groups are denoted by ^. For example, [aeiouAEIOU] would mean the expression can accept vowels, lowercase or uppercase. If written [^aeiouAEIOU] then it cannot include vowels.

### Greedy and Lazy Match
Greedy and Lazy match relates to Quantifiers. Greedy matches mean they match as many occurences of a pattern as possible. Lazy matches mean it will match as few occurrences as possible. 

### Boundaries
A word boundry is represented by \b and it matches positions where one side is a word character and the other side is not. For example, \bcat\b would match cat in black cat, but not catatonic. \bcat would match cat in catfish, and cat \b would match cat in tomcat, but not the other way around. \
(Rexegg.com)

### Back-references
A back-reference refers to a capturing group that matches the same characters more than once. \
(MDN web docs)

### Look-ahead and Look-behind
A look-ahead assertion attempts to match a following input with the given pattern. It is delineated by (?=pattern) or (?!pattern). A look-behind assertion does the same for the input behind it. It matches each pattern in reverse order. It is delineated by (?<=pattern) or (?<!pattern). \
(MDN web docs)


## Author

Stephanie DiLolle is an edX Bootcamp student. \
GitHub: github.com/stephdilolle

## References

https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial \
https://www.rexegg.com/regex-boundaries.php#anchors \
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Backreference \
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Lookahead_assertion \
https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Regular_expressions/Lookbehind_assertion 
