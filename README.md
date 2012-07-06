logifill-details
================

Polyfill for html5 details and summary elements.
This is an unobtrusive zero dependency implementation
of HTML5 details/summary implementation. As of May 2012,
only webkit browsers support it.

This polyfill adds full support for Firefox and IE8+.
In IE7 it works (almost) fine. But due to the lack of support
for :before, no arrow is shown before the summary elements.
This can be fixed by adding a padding and a background image
to the summary elements. For now, it is not a part of the
implementation. 

Unlike the other solutions, this one has two specific features:
1. It does not rely on jQuery or any other library.
2. It works for dynamic content because it does not attach
any event listeners to any summary or details elements.
There is a single listener that handles the click event
and reacts ONLY when the click happens on a summary element.

Usage
-----
Include this anywhere in your HEAD section: 
<script type="text/javascript" src="logifill-details.js"></script>
It does not add anything to the JavaScript global scope. 

Gotchas
-------
If details is used without a summary, there is no way to toggle the 
section, even though webkit browsers show a default summary in that case.
Direct text children of the summary elements are not invisible.
Wrapping these elements in a span or other element is a good idea.