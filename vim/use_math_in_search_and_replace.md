# Use math in Search and Replace

If you wish to search for numbers and replace each occurence by the result of an
expression like a math operation, you can use *sub-replace-expression*.

Help:

> Substitute with an expression           *sub-replace-expression*
>                         *sub-replace-\=*
> When the substitute string starts with "\=" the remainder is interpreted as an
> expression.  This does not work recursively: a substitute() function inside
> the expression cannot use "\=" for the substitute string.
>
> The special meaning for characters as mentioned at |sub-replace-special| does
> not apply except for "<CR>", "\<CR>" and "\\".  Thus in the result of the
> expression you need to use two backslashes to get one, put a backslash before a
> <CR> you want to insert, and use a <CR> without a backslash where you want to
> break the line.
>
> For convenience a <NL> character is also used as a line break.  Prepend a
> backslash to get a real <NL> character (which will be a NUL in the file).
>
> When the result is a |List| then the items are joined with separating line
> breaks.  Thus each item becomes a line, except that they can contain line
> breaks themselves.
>
> The whole matched text can be accessed with "submatch(0)".  The text matched
> with the first pair of () with "submatch(1)".  Likewise for further
> sub-matches in ().

Example:

Replace all numbers (which represent *minutes*) for their *hour* version:

`:%s:\<\d\+\>:\=submatch(0)/60:g`
