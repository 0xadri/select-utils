# select-utils documentation

## Goal

This tiny javascript utility library helps you sort any HTML's select element's options by value.

So for example:
  - if you have the options in the following order: Germany, Nepal, France, Honduras.
  - then when sorting this using this library, you will get the sort order: France, Germany, Honduras, Nepal.

Note that the initially selected option will stay as the option selected.


## Usage

`selectUtils.sortOptions(<jQuerySelector>);`

i.e. `selectUtils.sortOptions($('#select-country'));`

See live demo: https://jsfiddle.net/AdrienBe/9d7j8bcL/


## More on the implementation

This uses the best solution for a clean context-free natural sorting order of strings, that is: `.localeCompare()`


## Resources

http://stackoverflow.com/questions/45888/what-is-the-most-efficient-way-to-sort-an-html-selects-options-by-value-while

String comparison:
  http://stackoverflow.com/questions/51165/how-do-you-do-string-comparison-in-javascript
  http://stackoverflow.com/questions/2802341/natural-sort-of-text-and-numbers-javascript
  https://github.com/litejs/natural-compare-lite/issues/1
  https://github.com/javve/natural-sort/issues/7
  https://github.com/overset/javascript-natural-sort/issues/16
  Basic latin characters comparison using localeCompare() method http://jsbin.com/beboroyifomu/2/edit?js,console
  http://msdn.microsoft.com/en-us/library/ie/s4esdbwz(v=vs.94).aspx - IE6+ supports localeCompare() without the locales and options arguments
  https://code.google.com/p/v8/issues/detail?id=459 : highlight the sort order inconsistency across browser for localeCompare(), but it's still better than any custom implementation I could find

Module strategy based on :
 - comment of Maciej Baron on www.impressivewebs.com/my-current-javascript-design-pattern
 - presentation from Paul Irish https://www.youtube.com/watch?v=i_qE1iAmjFg
