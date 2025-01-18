# Unexpected Behavior with CSS calc()

This repository demonstrates an uncommon error that can occur when using the `calc()` function in CSS. Specifically, it highlights the issue of using percentages within the `calc()` function that are dependent on the element's final calculated width.

## The Problem
When using percentages inside a `calc()` expression, they are relative to the element's containing block. However, if the element's width itself is determined by the `calc()` expression, it might not be fully computed before the percentages are calculated, leading to unexpected behavior or even an infinite loop. 

The file `bug.css` illustrates this problem, while `bugSolution.css` presents a corrected version.

## How to Reproduce
1. Open `bug.html` in your web browser.
2. Observe the unexpected width of the element.
3. Open `bugSolution.html` and observe the corrected width.

## Solution
The solution involves restructuring the `calc()` expression to avoid circular dependencies. In many cases, using fixed pixel values or a different approach to sizing will resolve the issue.