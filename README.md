# Sass guide for getting things done.

This is a living document and new ideas are always welcome.

## Table of Contents

1. [Formatting](#1-formatting)
 - [80 character limit](#80-character-limit)
 - [Indentation](#indentation)

## 1. Formatting

Consistency is key.

### 80 character limit

There are other reasons for shorter lines, apart from history and screen sizes:

* Viewing code side by side (diffs, merges, etc).
* Viewing code in other media (Github, email, etc).
* Catching refactoring opportunities.
* Code readability (human eye can't scan long horizontal lines fast).

```scss
// Now, while it's still good practice to keep code below 80 columns, this 
// isn't one of those rules that needs to be followed religiously, contorting 
// yourself to make some line fit when it just doesn't. I suggest that you try 
// to keep all of your code under 80 columns, but when it just doesn't fit, 
// don't worry about it too much.
```

### Indentation

Use 4 space indentation

```scss
// Bad: 2 spaces
button {
  text-transform: uppercase;
}

// Good: 4 spaces
button {
    text-transform: upperace;
}
```
