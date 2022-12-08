# shy, an extremely minimal static site generator.

The idea for `shy` is that it reads files from an input directory and copies
them to an output directory, with one exception: markdown files get processed
by `cmark` and then pasted into the body of a template file.

It's not yet written, but the intent is that `shy` will be written in basic
POSIX shell, not using any bash-isms or other shell-specific -isms, so as to
work on the broadest number of platforms.

