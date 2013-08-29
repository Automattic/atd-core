## 24 Mar 10

*   Added L10n string _menu_title_confused_word_ to localize "Did you mean..."
*   Fixed two cases of parent variable polution (two for loops not declaring their vars)
*   Fixed bug preventing subsequent occurences of one error (w/ the same context) from highlighting
*   Error highlighter now uses beginning of word boundary to accurately find error location in text
*   Fixed bug preventing misspelled words in single quotes from being highlighted

## 28 Jan 10

*   Fixed a bug causing some errors to not get highlighted.

## 15 Jan 10

*   Fixed a bug with isMarkedNode (referred to the wrong variable which sometimes existed in the parent scope)
*   Fixed a bug with showTypes method not properly updating the list of types to show

## 4 Jan 10

initial release
