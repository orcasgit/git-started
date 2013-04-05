JavaScript Style Guide
======================

Location
--------
Almost all the JavaScript code should be broken out into JavaScript files, loaded in via `<script>`
tags at runtime. The `<script>` tags should all be loaded near the end of the HTML. The only times
JavaScript should be placed directly in the HTML is when you have variables that need to be populated
by the Django backend. These should all be in one place, just before the `<script>` tags for loading
in the JavaScript files.

Spacing
-------
Always tab with spaces and use 4 spaces per indentation level. Modularize the code as much as
possible and create named functions if necessary to prevent indentation from going way across the
screen. Generally speaking, if the code is indented more than 4 times, it is usually time to
restructure the code to reign it in.

Use two blank lines between classes, and one blank line between functions and other logical chunks.

Indentation should be done with
["the one true brace style"](http://en.wikipedia.org/wiki/Indent_style#Variant:_1TBS)(1TBS). An
example:
```javascript
if (test1) {
   function1();
} else {
   function2();
}
```

One of guidelines of note in `1TBS` is that the programmer should always use braces even for
single-line conditionals. This guideline prevents mistakes like:
```javascript
if (test1)
    function1(); // Only executed if test1 is true
    function2(); // Always executed, but maybe not expected
```
and
```javascript
// function2 always runs, but looks like part of the if statement
if (test1) function1(); function2();
else function3(); // Error
```

Object-Oriented
---------------
Treat JavaScript as if it is truly Object-Oriented, even though it is not technically true. Using a
framework like Backbone enables you to write pseudo-Object-Oriented code without trying too hard.
