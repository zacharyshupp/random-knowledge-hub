---
sidebar_position: 1
---

# Regular Expressions Basics

Regular expressions (regex) are sequences of characters that define search patterns. They are used for searching, matching, and manipulating strings in various programming languages and tools. This cheat sheet introduces basic regex concepts and syntax, along with examples to help beginners understand how to use them.

## Basic Syntax

This section covers fundamental regex symbols that represent common matching operations. These symbols help match specific patterns at the beginning or end of strings, match any character, and create optional, repeated, or alternative patterns.

| Symbol | Description                                                  | Example                                |
|--------|--------------------------------------------------------------|----------------------------------------|
| `.`    | Matches any character except newline.                        | `a.b` matches "acb", "aab", "a_b"      |
| `^`    | Matches the start of a string.                               | `^Hello` matches "Hello world"         |
| `$`    | Matches the end of a string.                                 | `world$` matches "Hello world"         |
| `*`    | Matches 0 or more of the preceding element.                  | `a*` matches "", "a", "aa"             |
| `+`    | Matches 1 or more of the preceding element.                  | `a+` matches "a", "aa", "aaa"          |
| `?`    | Matches 0 or 1 of the preceding element (optional).          | `colou?r` matches "color", "colour"    |
| `|`    | Logical OR between expressions.                              | `cat\|dog` matches "cat" or "dog"      |

## Character Classes

Character classes define a set of characters that can occur in a string at a particular position. They can specify individual characters or ranges and can also exclude characters.

| Syntax    | Description                                      | Example                          |
|-----------|--------------------------------------------------|----------------------------------|
| `[abc]`   | Matches any one of the enclosed characters.      | `[abc]` matches "a", "b", or "c" |
| `[^abc]`  | Matches any character not in the brackets.       | `[^abc]` matches "d", "e", etc.  |
| `[a-z]`   | Matches any character in the specified range.    | `[a-z]` matches "a" to "z"       |

## Predefined Character Classes

Predefined character classes are shorthand notations that match commonly used sets of characters, such as digits, word characters, and whitespace.

| Syntax | Description                                  | Example                         |
|--------|----------------------------------------------|---------------------------------|
| `\d`   | Matches any digit (0-9).                     | `\d` matches "1", "2", "3", etc.|
| `\D`   | Matches any non-digit character.             | `\D` matches "a", "!", etc.     |
| `\w`   | Matches any word character (alphanumeric + _)| `\w` matches "a", "1", "_"      |
| `\W`   | Matches any non-word character.              | `\W` matches " ", "!", "@"      |
| `\s`   | Matches any whitespace character.            | `\s` matches " ", "\t", "\n"    |
| `\S`   | Matches any non-whitespace character.        | `\S` matches "a", "1", "!"      |

## Quantifiers

Quantifiers specify how many times the preceding element should occur. They are used to match patterns that repeat a specific number of times.

| Syntax    | Description                                           | Example                          |
|-----------|-------------------------------------------------------|----------------------------------|
| `{n}`     | Matches exactly `n` occurrences of the preceding element. | `a{3}` matches "aaa"             |
| `{n,}`    | Matches `n` or more occurrences.                      | `a{2,}` matches "aa", "aaa", ... |
| `{n,m}`   | Matches between `n` and `m` occurrences.              | `a{2,4}` matches "aa", "aaa"     |

## Grouping and Capturing

Grouping allows you to treat multiple characters as a single unit. Capturing groups also store the matched content for later use. Non-capturing groups do not store matched content.

| Syntax       | Description                                                   | Example                     |
|--------------|---------------------------------------------------------------|-----------------------------|
| `(abc)`      | Groups expressions and captures the matched text.             | `(abc)` matches "abc"       |
| `(?:abc)`    | Non-capturing group; groups expressions without capturing.    | `(?:abc)` matches "abc"     |
| `(?<name>...)`| Named capturing group; captures with a name.                  | `(?<year>\d{4})` matches a four-digit year |

## Lookahead and Lookbehind

Lookahead and lookbehind assertions allow you to specify patterns that must (or must not) precede or follow a given position in the string, without including those patterns in the match.

| Syntax      | Description                                                  | Example                             |
|-------------|--------------------------------------------------------------|-------------------------------------|
| `(?=...)`   | Positive lookahead; asserts what follows is `...`.           | `a(?=b)` matches "a" if followed by "b" |
| `(?!...)`   | Negative lookahead; asserts what follows is not `...`.       | `a(?!b)` matches "a" if not followed by "b" |
| `(?<=...)`  | Positive lookbehind; asserts what precedes is `...`.         | `(?<=a)b` matches "b" if preceded by "a" |
| `(?<!...)`  | Negative lookbehind; asserts what precedes is not `...`.     | `(?<!a)b` matches "b" if not preceded by "a" |

## Special Sequences

Special sequences are shorthand notations for specific types of positions or characters within the string.

| Syntax | Description                                                | Example                              |
|--------|------------------------------------------------------------|--------------------------------------|
| `\b`   | Word boundary; matches the position between word and non-word characters. | `\bword\b` matches "word"            |
| `\B`   | Non-word boundary.                                         | `\Bword\B` matches "sword" in "password" |

## Escaping Special Characters

Special characters in regex have specific meanings. To match these characters literally, you need to escape them with a backslash (`\`).

| Character | Escaped Version | Example                  |
|-----------|-----------------|--------------------------|
| `.`       | `\.`            | `\.` matches a literal dot (.) |
| `*`       | `\*`            | `\*` matches a literal asterisk (*) |

## Examples

This section provides practical examples of regex patterns and their uses, demonstrating how to match common patterns like phone numbers, email addresses, and URLs.

| Pattern                               | Description                                        | Example Match                       |
|---------------------------------------|----------------------------------------------------|-------------------------------------|
| `\d{3}-\d{3}-\d{4}`                   | Matches a phone number in the format 123-456-7890. | "123-456-7890"                      |
| `[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}` | Matches an email address. | "example@example.com"              |
| `https?://[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}(/[^ ]*)?` | Matches a URL.                  | "http://www.example.com"            |

---

Regular expressions are a powerful tool for searching and manipulating text. This cheat sheet covers the basics, but regex can be used for much more complex patterns and operations. Practice using these concepts to get comfortable with regular expressions and explore their full potential!
