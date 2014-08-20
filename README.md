# sqlup-mode

`sqlup-mode` is a minor mode for emacs. Its sole purpose is to make
your life easier when writing SQL.

SQL, by convention, uses upper-case keywords, although lower-case
works just as well. As humans, the separation between upper-case and
lower-case helps scan and parse the code much more quickly.

## Installation

### Manually

Content TK. Pull request welcome. Same as all other emacs packages,
really.

### MELPA

sqlup-mode is on MELPA.

### Marmalade

sqlup-mode is NOT YET on Marmalade.

## Usage

### Setup

Here follows an example setup to activate `sqlup-mode` automatically when entering sql-mode or sql-interactive-mode:

``` lisp
(add-hook 'sql-mode-hook 'sqlup-mode)
(add-hook 'sql-interactive-mode-hook 'sqlup-mode)
```

### Normal typing (e.g. SQL REPL)

Activate the minor mode with `M-x sqlup-mode` and you can just start
typing. The minor mode will be triggered by the following keys:
* `SPC`
* `(`
* `,`
* `;`
* `\r` (Enter)

### Work with a region

Select a region and just call `M-x sqlup-capitalize-keywords-in-region`.
Magic.


## Implementation choices

I made the choice of only triggering the word-scanning when a particular keypress happens specifically because I don't want to see the word "ORde" typed when I'm typing "ORDER", and I didn't know a *simple* way to do it. I believe that in practice, this is good enough.
