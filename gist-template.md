# Title (replace with your title)

Introductory paragraph (replace this with your text)

## Summary
We will be evaluating the following regular expressions used to match HEX values:

/^#?([a-f0-9]{6}|[a-f0-9]{3})$/


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
The two principal anchors in this regex expression are the `^` at the beginning and the `$` at the end which constitute an exact string match with the components included within the two anchors. When used alone, the `^` anchor matches any string that *begins* with the characters that follow the anchor. The `$` matches any string that *ends* with the characters that precede it. By enclosing the regex between these two anchors, we are asking the search function to match exactly is included between them (what it begins AND ends with). 
### Quantifiers
So what is included between the two anchors. If we examine the expression, we can see that there are a number of components separated by parentheses `()`. Parentheses are used in regex to create separate groups of interest. Within each of these groups, there is a regex that we may look at separately to see what is evaluated. These include:
- the initial `https` component: `(https?:\/\/)`
- the domain name (e.g. `www.google`, or `pets`): `([\da-z\.-]+)\.`
- the top level domain (`.com`, `.gov`, etc): `([a-z\.]{2,6})`
- the file path: `([\/\w \.-]*)*`

### OR Operator
some of the components of *capture groups* end with a `?` or a `*`. These are generally known as **quantifiers**. Quantifiers are used to define the number of times a given expression may be identified. The `?` makes a single instance of the character preceding the quantifier optional, whereas the `*` makes multiple instances of the characters preceding the quantifier optional. 
For example, the grouping 
```
(https?:\/\/)?
```
contains two `?` quantifiers. This expression is looking for an `http://`
So if we look at the fourth grouping:
```
([\/\w \.-]*)*
```
The expression is allowing for any number of filepath characters that may follow an initial specified domain.

Finally, the `{}` quantifier defines a range of possible instances where a match may be identified. In evaluating the Top level domain, the regular expression allows for the top level domain to consist of 2 to 6 characters.
### Character Classes
The main character classes to consider in the above expression include the \d character class which looks for any digit, and the \w character class that looks for any alphanumeric character.
### Flags
i
With this flag the search is case-insensitive: no difference between A and a.
g
With this flag the search looks for all matches, without it – only the first match is returned.
m
Multiline mode (covered in the chapter Multiline mode of anchors ^ $, flag "m").
s
Enables “dotall” mode, that allows a dot . to match newline character \n.
u
Enables full Unicode support. The flag enables correct processing of surrogate pairs. More about that in the chapter Unicode: flag "u" and class \p{...}.
y
“Sticky” mode: searching at the exact position in the text (covered in the chapter Sticky flag "y", searching at position)
### Grouping and Capturing
Parentheses group the regex between them. They capture the text matched by the regex inside them into a numbered group that can be reused with a numbered backreference. They allow you to apply regex operators to the entire grouped regex.
### Bracket Expressions
The main OR operator used in the above regex is the `[]`. The expression will match for any characters or character classes included in the brackets. For example the `[\da-z\.-]` expression matches for any digits (`\d`) OR any characters between a and z (`a-z`) OR any '.' (`\.`) OR any '-' (`-`). 
### Greedy and Lazy Match
Code Snipet: [a-f0-9]{6} Code Snipet: [a-f0-9]{3}

Quantifier: {}

Description: Greedy means match the longest possible string. Lazy means match the shortest possible string.

Example: w.+l matches well in well but the lazy w.+?l matches wel

As explained in the quantifier section, normal quantifiers are greedy, causing the regex to match as many occurrences of a particular pattern as possible. However, if ? was appended, the quantifier would become lazy-- causing the regex to match as few occurrences as possible. In our case, the quantifier is greedy.
### Boundaries
Boundary markers such as ^ and $ allow you to anchor the regex pattern to the beginning and end of the line (or string depending on which flags you use).
### Back-references
Backreferences match the same text as previously matched by a capturing group
### Look-ahead and Look-behind
Negative lookahead provides the solution: q(?!u). The negative lookahead construct is the pair of parentheses, with the opening parenthesis followed by a question mark and an exclamation point.

## Author

Troy Miller github@ https://github.com/R0x0s  email: troysteedmiller@gmail.com
