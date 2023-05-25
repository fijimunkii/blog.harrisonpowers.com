---
layout: post
title: CSS Pseudo Classes and Elements
categories:
- css
tags: []
---
I'm not about to explain how to use these, or what they are. This is simply a handy dandy list of CSS pseudo classes and elements that you can use.

```css
:hover
:focus
:target
:active
:visited

:enabled
:disabled
:checked
:indeterminate

:root
:first-child
:last-child
:only-child
:nth-child(n)
	:nth-child(even)
	:nth-child(odd)
	:nth-child(2n) /* Even */
	:nth-child(2n+1) /* Odd */
	:nth-child(3n) /* Every 3rd element */
	:nth-child(4n+1) /* Every 4th element starting with the 1st */
:nth-of-type(n) /* Like :nth-child, but used where elements at the same level are of different types */
:first-of-type
:last-of-type
:nth-last-of-type(n) /* like nth-of-type, but counts up from the bottom */
:nth-last-child(n) /* like nth-child, but counts up from the bottom */
:only-of-type /* selects only if the element is the only one of its kind within the parent */
:not(s) /* selects all except the parameter */
:empty /* selects elements which contain no text and no child elements */

:first-letter
:first-line
:lang

::selection
::-moz-selection

:before
:after
```
