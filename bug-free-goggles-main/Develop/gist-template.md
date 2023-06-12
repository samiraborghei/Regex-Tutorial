# Module 17 (Regex-Tutorial)

Regex (Regular expressions) are a powerful tool for searching text as well as for searching and replacing text. With the help of regular expressions and suitable text editors such as the TextConverter, the editing of texts can be made much easier.

## Summary


I want to write a regular expression for a standard US type phone number that supports the following formats:
###-###-####
(###) ###-####
### ### ####
###.###.####
where # means any number.

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
Regexes are composed of several different components that work together to define a search pattern. The most common components include anchors, character classes, quantifiers, and alternation.

### Anchors
So far I came up with the following expressions
^[1-9]\d{2}-\d{3}-\d{4}
^\(\d{3}\)\s\d{3}-\d{4}
^[1-9]\d{2}\s\d{3}\s\d{4}
^[1-9]\d{2}\.\d{3}\.\d{4}

I modify the expression/expressions so that I can also include a condition to support the area code as optional component. Something like this:
+1 ### ### ####
where +1 is the area code and it is optional.

### Quantifiers
Quantifiers are used to communicate how many characters are expected. Quantifiers specify how many instances of a character, group, or character class must be present in the input for a match to be found. By default, quantifiers are greedy, and will match as many characters as possible.
You could use a regex of account ([0-9]+). In this regex, ([0-9]+) forms a group which will match the actual account number, which we can back reference as $1 in our replacement string, which becomes acct $1.

### OR Operator
The logical OR (||) (logical disjunction) operator for a set of operands is true if and only if one or more of its operands is true. It is typically used with boolean (logical) values. When it is, it returns a Boolean value. However, the || operator actually returns the value of one of the specified operands, so if this operator is used with non-Boolean values, it will return a non-Boolean value.

### Character Classes
^(\+\d{1,2}\s)?\(?\d{3}\)?[\s.-]\d{3}[\s.-]\d{4}$
Character classes are components within our regular expression that tells us what type of characters to expect. In our example our character classes are confined within brackets []. This is the matches the following 
123-456-7890
(123) 456-7890
123 456 7890
123.456.7890
+91 (123) 456-7890

### Flags
A flag is an optional parameter to a regex that modifies its behavior of searching. A flag changes the default searching behavior of a regular expression. It makes a regex search in a different way. A flag is denoted using a single lowercase alphabetic character.
There are two syntaxes that can be used to create a regular expression object.

The “long” syntax:

regexp = new RegExp("pattern", "flags");
And the “short” one, using slashes "/":

regexp = /pattern/; // no flags
regexp = /pattern/gmi; // with flags g,m and i (to be covered soon)


### Grouping and Capturing
In the case of our regex, we have used grouping constructs to create different sections, known as subexpression, within our regex: ([a-z0-9_\.-]+), ([\da-z\.-]+), and ([a-z\.]{2,6}). To create a subexpression, simply wrap it in parentheses.

### Bracket Expressions
Brackets indicate a set of characters to match. Any individual character between the brackets will match, and you can also use a hyphen to define a set.

'elephant'.match(/[abcd]/) // -> matches 'a'
You can use the ^ metacharacter to negate what is between the brackets.

'donkey'.match(/[^abcd]/) // -> matches 'o'

You will often see ranges of the alphabet or all numerals. [A-Za-z] [0-9] Remember that these character sets are case sensitive, unless you set the i flag.

'elephant'.match(/[a-d]/) // -> matches 'a'
'elephant'.match(/[A-D]/) // -> no match
'elephant'.match(/[A-D]/i) // -> matches 'a'

### Greedy and Lazy Match
A greedy match tries to match an element as many times as possible. Whereas, a lazy match tries to match an element as few times as possible.
In my example greedy quantifier is * and lazy quantifier is *? the description is star quantifier: 0 or more.


### Back-references
My refrences are:
www.stackoverflow.com
www.sttmedia.com
www.computerhope.com



## Author

Hi I'm Samira, I'm studing full stack coding at GWU. 
If you like you can look at my GitHub and portfolio.
GitHub: https://github.com/samiraborghei 
Portfolio: https://samiraborghei.wordpress.com