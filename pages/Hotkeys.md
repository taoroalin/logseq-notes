---
title: Hotkeys
---

## Ideal
### Movement
#### generalized "to end of form" and "to beginning of form"

#### File top + bottom

### Generalized Slurp / Barf
#### inside c-style brackets moves brackets down a line

#### in python (or generally outside all brackets and inside tabbed region) indent the next line

## Current
### non-lisp
#### expand selection: Shift Alt Right

#### Python Exec Line/Selection: Shift Enter

#### Next / Pervious Line Same Indent (Select): Ctrl (Shift) Up/Down

#### Next / Previous Word: Ctrl Right / Left

### Lisp
#### Slurp/Barf Front: Ctrl Right / Left

#### Slurp/Barf Back: Ctrl Shift Right / Left

#### Forward/Backward (Select) Form: Ctrl Alt (Shift) Right/Left

#### Forward Down / Backward Up: Ctrl Down / Up

#### Convolute Sexp: Ctrl Shift C
##### __actually called__ Envelop Form https://stackoverflow.com/questions/18192010/whats-the-use-for-paredit-convolute-sexp-in-paredit-mode

#### Splice: Ctrl Alt s
##### barfs everything out of current parens, and deletes said parens

#### Splice Delete Backward/Forward: Ctrl Shift Alt Backspace/Delete
##### Back is more useful, and it means "get rid of this function, and move its arguments down into the enclosing function"
