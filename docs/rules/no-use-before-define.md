---
title: ESLint
layout: doc
---
<!-- Note: No pull requests accepted for this file. See README.md in the root directory for details. -->
# Disallow Early Use

Since variable and function declarations are hoisted to the top of a scope, it's possible to use identifiers before their formal declarations in code. This can be confusing and some believe it is best to always declare variables and functions before using them.

```js
alert(a); 

var a = 10;
```

## Rule Details

This rule will warn when it encounters a reference to an identifier that has not been declared as part of a `var` or function statement.

The following patterns are considered warnings:

```js
alert(a); 
var a = 10;

f(); 
function f() {}
```

The following patterns are not considered warnings:

```js
var a = 10; alert(a);

function f() {} f();
```
