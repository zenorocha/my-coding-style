# My Coding Style

For years I've been using different coding conventions for JavaScript development.

But after reading [Nicholas Zakas's book](http://shop.oreilly.com/product/0636920025245.do) and inspired by [@zeh](https://github.com/zeh/), I've decided to formalize my reasons behind some of the conventions I adopted. Feel free to suggest anything you want :)

> "All code in any code-base should look like a single person typed it, no matter how many people contributed."

## Commits

Don't use Past or Present Continuous tenses for commit messages, those should be in Imperative Present tense.

```javascript
// Good
Add feature X

// Bad
Added feature X
Adding feature X
```

Every commit message needs to be in English, doesn't matter what's your native language.

> Reason: TODO

## Indentation

The unit of indentation is **4 spaces**. Never mix spaces and tabs.

```javascript
// Good
while (condition) {
    statements
}

// Bad
while (condition) {
  statements
}
```

> Reason: TODO

## Line length

Avoid lines longer than **80 characters**. When a statement will not fit on a single line, it may be necessary to break it. Place the break after an operator, ideally after a comma. The next line should be indented **4 spaces**.

```javascript
// Good
YUI().use('aui-module-a', 'aui-module-b', 'aui-module-c', 'aui-module-d',
    'aui-module-e', 'aui-module-f');

// Bad
YUI().use('aui-module-a', 'aui-module-b', 'aui-module-c', 'aui-module-d', 'aui-module-e', 'aui-module-f');
```

Every project should contain a [.editorconfig](https://github.com/zenorocha/my-coding-style/blob/master/.editorconfig) file that automatically set some indentation definitions. Make sure to install [Editor Config's](http://editorconfig.org/) plugin on your code editor and you'll be all set.

> Reason: TODO

## Linting

Use [JSHint](http://www.jshint.com/) to detect errors and potential problems.

The options for JSHint are stored in a [.jshintrc](https://github.com/zenorocha/my-coding-style/blob/master/.jshintrc) file.

> Reason: TODO

## Semicolons

Relying on ASI (Automatic Semicolon Insertion) can cause hard to debug problems, so don't do it. **Always** use semicolons.

```javascript
// Good
a = b + c;
test();

// Bad
a = b + c
test()
```

> Reason: TODO

## Variables

All variables should be declared **before** used. Avoid multiple var statements.

```javascript
// Good
var foo = '',
    bar = '';

// Bad
var foo = '';
var bar = '';
```

Constants (variables with permanent values) are written **uppercase**.

```javascript
// Good
var FOO = 'foo';

// Bad
var foo = 'foo';
```

> Reason: TODO

## Strings

Prefer single quotes over double quotes.

```javascript
// Good
var string = '<p class="foo">Lorem Ipsum</p>';

// Bad
var string = "<p class='foo'>Lorem Ipsum</p>";
```

Hexidecimal colors are written **uppercase**.

```javascript
// Good
var color = '#D96AB6';

// Bad
var color = '#d96ab6';
```

> Reason: TODO

## New lines

Parentheses `()` and commas `,` are **not** followed by indented children on new lines.

```javascript
// Good
YUI().use('aui-module', function (Y) {
    statements
});

// Bad
YUI().use(
    'aui-module',
    function (Y) {
        statements
    }
);
```

Curly brackets `{}` are followed by **new lines** and indented children.

```javascript
// Good
if (condition) {
    statements
}
else {
    statements
}

// Bad
if (condition) {
    statements
} else {
    statements
}
```

> Reason: TODO

## Whitespace

Add spaces between **operators** (`=`, `>`, `*`, etc).

```javascript
// Good
for (i = 0; i < 10; i++) {
    statements
}

// Bad
for (i=0;i<10;i++) {
    statements
}
```

Both function expressions and function declarations **doesn't** have a space between the function keyword and the function name.

```javascript
// Good
var foo = function() {
    statements
};

// Bad
var foo = function () {
    statements
};

// Good
function bar() {
    statements
}

// Bad
function bar () {
    statements
}
```

Add spaces **outside** parentheses `()` but avoid it inside.

```javascript
// Good
if (x > 10) {
    statements
}

// Bad
if( x > 10 ){
    statements
}
```

Empty lines have no trailing spaces.

> Reason: TODO

## Conditionals

Avoid inline conditionals. Every conditional (with single or multiple statements) should use **curly brackets** `{}`. The only exception to this rule is `else if`.

```javascript
// Good
if (condition) {
    statements
}
else if (condition) {
    statements
}
else {
    statements
}

// Bad
if (condition) statement;
else if (condition) statement;
else statement;
```

> Reason: TODO

## Equality

Strict equality checks `===` should be used in favor of `==`.

```javascript
// Good
if (foo === 'foo') {
    statement
}

// Bad
if (foo == 'foo') {
    statement
}

// Good
if (bar !== 'bar') {
    statement
}

// Bad
if (bar != 'bar') {
    statement
}
```

> Reason: TODO

## Loops

Avoid inline loops. Every loop (with single or multiple statements) should use **curly brackets** `{}`.

```javascript
// Good
for (initialization; condition; expression) {
    statements
}

// Bad
for (initialization; condition; expression) statement;
```

> Reason: TODO

## References

* [Google JavaScript Style Guide](http://google-styleguide.googlecode.com/svn/trunk/javascriptguide.xml)
* [Douglas Crockford's Code Conventions for JavaScript](http://javascript.crockford.com/code.html)
* [idiomatic.js](https://github.com/rwldrn/idiomatic.js/)
* [jQuery JavaScript Style Guide](http://contribute.jquery.org/style-guide/js/)
