#!/usr/bin/sh
#Copyright (C) 2025 by john morris beck <john.morris.beck@hotmail.com>
#
#Permission to use, copy, modify, and/or distribute this software for any purpose with or without fee is hereby granted.
#
#THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES WITH REGARD TO THIS SOFTWARE INCLUDING ALL
#
#IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES WHATSOEVER
#
#RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF OR IN CONNECTION WITH THE USE OR PERFORMANCE OF
#
#THIS SOFTWARE.
mmcr is a very tiny posix macro system designed to give you a series of reader macros to a language where the macros have macros. it is a
hack that allows you to change the way any programming language is written while it is running.

Lets apply mmcr to the program python3:

sh|sh|python3<&2

to understand how this program can do anything at all a good exercise is to try to print something using this language. this can be done with

echo echo "\"print(\\\"hello\\\");\""

essentially every line of code passes between two posix shells. this means that the posix shell has an opportunity to manipulate the code that passes
through it.

the first shell in the pipeline is designed to manipulate the syntax of the second shell. the second shell in the pipeline is designed to edit the syntax
of the interpreter at the end of the pipeline. thus with this setup it is possible to manipulate the syntax of python with reader macros.

in order to work in a more compiled fashion one can do something like

cat my_c_program.c | sh | sh > outputfile.c

because of the very small size of mmcr, it is not a legally copyrightable program. extremely small programs such as this that are only a few characters long
can not be legally copyrighted or patented due to their small sizes.

you may ask "memesmith, why do you have a copyright license on your program knowing that it can't be copyrighted."

This license is a warning to the user that the software does not come with any guarantee of merchantibility or fitness, rather than something to try to
control what the user is allowed to do with the code.


disregard all of the above bullshit

this is an explanation of mmcr

you pipe sh into sh like so: sh | sh

what this does is it creates a one line non copyrightable way to add syntax macros to posix shell (thus why we use sh instead of bash).

instead of typing echo hello you have to type echo "echo hello" to get anything to print

thus the first instance of sh acts as a preprocessor and the second instance of sh is the runtime
