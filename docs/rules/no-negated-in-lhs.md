---
title: ESLint
layout: doc
---
<!-- Note: No pull requests accepted for this file. See README.md in the root directory for details. -->
# no negated left operand of `in` operator

## Rule Details

This error is raised to highlight a potential error. Commonly, when a developer intends to write

```js
if(!(a in b)) // do something
```

they will instead write

```js
if(!a in b) // do something
```

If one intended the original behaviour, the left operand should be explicitly coerced to a string like below.

```js
if(('' + !a) in b) // do something
```

## When Not To Use It

Never.

## Further Reading

None.
