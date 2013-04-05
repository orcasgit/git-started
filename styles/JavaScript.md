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
screen. Generally speaking, if the code is indented more than 5 times, it is time to restructure the
code to reign it in.

Object-Oriented
---------------
Treat JavaScript as if it is truly Object-Oriented, even though it is not technically true. Using a
framework like Backbone enables you to write pseudo-Object-Oriented code without trying too hard.
