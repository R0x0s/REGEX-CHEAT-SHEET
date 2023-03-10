# Title (replace with your title)

Introductory paragraph (replace this with your text)

## Summary

Briefly summarize the regex you will be describing and what you will explain. Include a code snippet of the regex. Replace this text with your summary.

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
