# RegEx Simplified

Regex stands for regular expression, which is a sequence of characters that defines a specific search pattern. It uses code and algorithms to find certain patterns, such as phone numbers, HTML tags, etc. In today's example, we will focus on finding email addresses.

## Summary

Today I will be explaining this pile of code here: ^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+.[a-zA-Z]{2,}$. What type of tomfoolery is this?! Up until today, I had no idea, but hopefully, I can simplify things a bit to give you a better understanding.

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

^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$

In this code snippet, the ^ and the $ are acting as anchors. What that means is that the ^ is the starting point, telling the program where to begin, and the $ is the marker indicating where to stop. These symbols aren't used as characters to search for, but rather as signals to start and stop, similar to the start line and the finish line of a race.

### Quantifiers

Quantifiers specify how many instances of a character or groups of characters are expected. They essentially set rules and limits for what the string can and cannot have. The + in the regex signifies 'one or more', indicating that there must be one or more lowercase, uppercase, number, or symbol in the email address. The {2,} part of the regex matches two or more occurrences of letters in the top-level domain (TLD).

### OR Operator

An OR operator allows you to match a pattern with alternatives. It allows you to specify multiple alternatives and if any of those alternatives match the input string, the regex engine considers the match successful.

OR operators are marked with an | and a popular way this OR operator is used is in date regex. 👉
^(0[1-9]|1[012])[-/.](0[1-9]|[12][0-9]|3[01])[-/.][0-9]{4}$

In the first group of code, it states you can pick a month starting with 0 OR (|) 1.

### Character Classes

Character classes in regex are shortcuts to include specific sets of characters. They're denoted by a backslash followed by a character. These shortcuts help simplify regex patterns by representing sets of characters concisely.

\d represents any digit (same as [0-9]).
\b sets a word boundary. For example, \bsand matches "sand" but not "quicksand."
\w represents word characters, including letters (both uppercase and lowercase), digits, and underscore.

### Flags

Flags in regex modify how the pattern search works. These flags help you customize how regex patterns are matched in a string. Here are a few common ones in JavaScript =>

i (ignore case): Matches regardless of letter casing. For example, it matches both "Go" and "go".
g (global): Searches for all instances of the pattern in the string.
s (dot all): Allows the dot . character to match any character, including newline.
m (multiline): Affects ^ and $ anchors, allowing them to match the start and end of each line in a multi-line string.

### Grouping and Capturing

Grouping or capturing groups in regex lets you combine specific characters or strings into a single unit. In the email example ^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$, the characters inside square brackets [...] form a group. This group represents a specific pattern in the email address

When you use groups, the regex engine remembers them and can use them later. This helps you define search criteria for specific parts of a string.

For instance, in an email regex, you can have a group for the username part, a group for the domain name, and so on. This way, you can work with different parts of the email address separately

### Bracket Expressions

A bracket expression in regex helps you specify which characters you want to match. You put the characters you're interested in inside square brackets, like [...]. For example, [0-9] matches any digit from 0 to 9, and [a-z] matches any lowercase letter from a to z. It lets you define specific character choices for your pattern

### Greedy and Lazy Match

In regex, there's a concept of being "greedy" or "lazy". When a regex is greedy, it tries to match as much of the input as it can. For example, using \* in a regex will match as many characters as possible, including partial matches, single characters, or complete strings.

On the other hand, if you use ? in your regex, it becomes "lazy". A lazy regex tries to find the smallest possible match. It stops as soon as it finds the first occurrence that fits the pattern, instead of grabbing as much as it can.

So, being greedy means grabbing a lot, while being lazy means grabbing as little as possible to make a match.

### Boundaries

Boundaries in regex are like markers that help you find specific words or patterns in a string. You use \b to indicate these boundaries. For example, \bcat\b would find the word "cat" in a sentence like "The cat is cool," but not in a phrase like "catch a train." It ensures you're matching whole words, not parts of words.

### Back-references

Back-references in regex allow you to reuse previously captured groups. You can refer back to a specific group in your pattern. For example, if you captured a character inside parentheses like (a), you can refer to it later using \1. So, ([abc])\1 would match a letter (a, b, or c) and then match the same letter again later in the string. It helps you find repeating patterns in text.

### Look-ahead and Look-behind

In regex, (?<=...) is a lookbehind. It means checking what comes after a specific phrase in a text. For instance, (?<=The Cat is).\* would highlight the word "Fuzzy" in the text "The Cat is Fuzzy" because it looks for what comes after "The Cat is."

On the other hand, there's a lookahead, which checks what comes before a specific phrase in a text. It's like looking ahead to see if certain characters exist before a word or phrase you're interested in.

## Author

Kenneth Lau 💪😉👌

Up in coming full stack web developer

GitHub https://github.com/Kenlau94

Repo https://github.com/Kenlau94/RegEx-QuestionMark

## Useful sources

Regex Email https://www.youtube.com/watch?v=QxjAOSUQjP0

Gist Intro https://www.youtube.com/watch?v=aCdKx__VabQ

Regex Intro https://www.youtube.com/watch?v=7DG3kCDx53c

Regex Intro PT2 https://coding-boot-camp.github.io/full-stack/computer-science/regex-tutorial

![image](https://user-images.githubusercontent.com/134185724/275365427-030da588-62d3-4ce6-9864-c154dce76ae4.png)
