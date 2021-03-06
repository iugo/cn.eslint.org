---
title: Rule no-unneeded-ternary
layout: doc
---
<!-- Note: No pull requests accepted for this file. See README.md in the root directory for details. -->
# Disallow boolean literals in conditional expressions (no-unneeded-ternary)

It's a common mistake in JavaScript to use a conditional expression to select between two Boolean values instead of using ! to convert the test to a Boolean.
Here are some examples:

```js
// Bad
var isYes = answer === 1 ? true : false;

// Good
var isYes = answer === 1;


// Bad
var isNo = answer === 1 ? false : true;

// Good
var isYes = answer !== 1;
```

This rule disallows the use of 'Boolean' literals inside conditional expressions.

## Rule Details

This rule enforces a coding style where it disallows the use of Boolean literals inside conditional expressions.

The following patterns are considered warnings:

```js
var a = x === 2 ? true : false;

var a = x ? true : false;
```

The following patterns are not considered warnings:

```js
var a = x === 2 ? "Yes" : "No";

var a = x !== false;
```

## When Not To Use It

You can turn this rule off if you are not concerned with booleans in conditional expressions.

## Version

This rule was introduced in ESLint 0.21.0.

## Resources

* [Rule source](https://github.com/eslint/eslint/tree/master/lib/rules/no-unneeded-ternary.js)
* [Documentation source](https://github.com/eslint/eslint/tree/master/docs/rules/no-unneeded-ternary.md)
