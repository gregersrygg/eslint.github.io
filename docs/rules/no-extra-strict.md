---
title: ESLint
layout: doc
---
<!-- Note: No pull requests accepted for this file. See README.md in the root directory for details. -->
# Disallow Unnecessary Strict Pragma

The `"use strict";` directive applies to the scope in which it appears and all inner scopes contained within that scope. Therefore, using the `"use strict";` directive in one of these inner scopes is unnecessary.

```js
"use strict";

(function () {
    "use strict";
    var foo = true;
}());
```

## Rule Details

This rule is aimed at preventing unnecessary `"use strict";` directives. As such, it will warn when it encounters a `"use strict";` directive when already in strict mode.

The following patterns are considered warnings:

```js
"use strict";

(function () {
    "use strict";
    var foo = true;
}());
```

The following patterns are not considered warnings:

```js
"use strict";

(function () {
    var foo = true;
}());
```



```js
(function () {
    "use strict";
    var foo = true;
}());
```

## Further Reading

* [The ECMAScript 5 Annotated Specification - Strict Mode](http://es5.github.io/#C)
