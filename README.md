# `shy`, an extremely minimal static site generator.


`shy` reads files and directories from a source directory and copies them to
a destination directory; if a file is Markdown, it gets processed by `cmark`
and put into a template, and then placed in the destination directory as an
`.html` file.

`shy` recognizes the following file extensions as Markdown:

- `.md`
- `.markdown`
- `.mdown`
- `.mdwn`
- `.mkd`
- `.mkdn`
- `.mkdown`

Everything else is not-Markdown and will be copied without processing.

If no Markdown files are found within the source directory, then the template
parameter is optional. In that situation you should probably just use `cp -R`
to recursively copy the directory.

## Usage

The `shy` help text reads as follows:

```
USAGE:
  shy [ OPTIONS ] [ FLAGS ]

OPTIONS:
  -s <SOURCE DIR>        the source folder to scan [default ./src]
  -d <DESTINATION DIR>   where to write the outputs [default: ./dest]
  -t <TEMPLATE FILE>     the HTML template to put Markdown into [default: template.html]
  -v                     run with verbose output

FLAGS:
  -V   print the version number and exit
  -h   print the help text and exit

EXAMPLE:
  shy -s src -d dest -t template.html

MORE INFO:
  By default, shy outputs nothing to the user unless an error arises.
  shy relies on cmark being installed on the target system; if cmark is not
  installed, shy will exit with an error.

CREDITS:
  Written by Andrew Lilley Brinker <alilleybrinker@gmail.com>.
```

## Template File

`shy` comes with an example `template.html` file. The file can contain whatever you
want, so long as it has a `{{ content }}` string, which will be replaced with the
output of running `cmark` against any Markdown files found during processing of the
source directory.

## License

`shy` is MIT licensed.

## Contribution

Contributions for bug-fixes and greater cross-platform compatibility are
welcome, but additional features / flags are not. Staying extremely simple
and not-at-all-configurable is a core goal of `shy`.

If you want to add more features, feel free to create your own fork!

