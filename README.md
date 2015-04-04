# Sass guide for getting things done.

This is a living document and new ideas are always welcome.

## Table of Contents

1. [Formatting](#1-formatting)
 - [80 character limit](#80-character-limit)
 - [Border](#border)
 - [Capitalization](#capitalization)
 - [Color](#color)
 - [Declaration Order](#declaration-order)
 - [Indentation](#indentation)
 - [Leading Zero](#leading-zero)
 - [Url Quotes](#url-quotes)
2. [Comments](#2-comments)
 - [Section](#section)
 - [Sub-section](#sub-section)



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

### Border

Prefer `border: 0;` over `border: none;`.

```scss
// bad
.selector {
    border: none;
}

// good
.selector {
    border: 0;
}
```

### Capitalization

IDs, classes, types, placeholders, and pseudo-selectors should be all lowercase.

```scss
// bad
.Selector {}

// good
.selector {}
```

### Color

Prefer hexadecimal color codes over color keywords.

```scss
// bad: color keyword
$color-brand: black;

// good: hexadecimal color
$color-brand: #000;
```

### Declaration Order

Rule sets should be ordered as follows: `@extend` declarations, `@include`
declarations, then nested rule sets.

```scss
// bad
.selector {
    padding: 10px;
    @include box();
    @extend %clearfix;
}

// good
.selector {
    @extend %clearfix;
    @include box();
    padding: 10px;
}
```

### Indentation

Use 4 space indentation.

```scss
// bad: 2 spaces
.selector {
  text-transform: uppercase;
}

// good: 4 spaces
.selector {
    text-transform: uppercase;
}
```

### Leading Zero

Don't write leading zeros for numeric values with a decimal point.

```scss
// bad: unnecessary leading zero
.selector {
    padding: 0.75em;
}

// good: no leading zero
.selector {
    padding: .75em;
}
```

### Url Quotes

URLs should always be enclosed within quotes.

Using quoted URLs is consistent with using other Sass asset helpers, which also
expect quoted strings. It also works better with most syntax highlighters, and
makes it easier to escape characters, as the escape rules for strings apply,
rather than the different set of rules for literal URLs.

```scss
// bad: no enclosing quotes
.selector {
    background: url(example.png);
}

// good
.selector {
    background: url("example.png");
}
```

## 2. Comments

Well commented code is extremely important.

### Section

Begin every section block with a title.

```scss
// *************************************
//
//   #SECTION-TITLE
//
// *************************************

.selector {}
```

Each title should be preceded by five (5) carriage returns.

```scss
// *************************************
//
//   #SECTION-ALPHA
//
// *************************************

.selector-alpha {}





// *************************************
//
//   #SECTION-BETA
//
// *************************************

.selector-beta {}
```

### Sub-section

Begin every sub-section block with a title.

```scss
//   #SUB-SECTION-TITLE
// *************************************

.selector {}
```

Prefer `//` comments over `/* ... */`.

```scss
// bad
/* This is a comment that gets rendered. */

// good
// This comment never gets rendered.
```
