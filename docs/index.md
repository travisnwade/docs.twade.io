# Travis Wade Documentation Wiki

## How this site got started
### MKDocs
For full documentation visit [mkdocs.org](https://www.mkdocs.org).

### Footnotes

This is an example of a footnote[^1] 

[^1]: 
    This is the description of the footnote itself. 
    Which should render at the bottom of the page. 
    For more reading, read here: [python-markdown-extension-footnotes](https://python-markdown.github.io/extensions/footnotes/)

## Where I host this
### Netlify
I host this site completely on [Netlify](https://www.netlify.com/) on a free account. But that also comes with custom domain, free HTTPS. Which is badass!

There's no database to manage, just simple, flat files that I can write content using markdown, and one simple command that generates all static HTML files.

## Included documentation
### Commands

* `mkdocs new [dir-name]` - Create a new project.
* `mkdocs serve` - Start the live-reloading docs server.
* `mkdocs build` - Build the documentation site.
* `mkdocs -h` - Print help message and exit.

### Project layout

    mkdocs.yml    # The configuration file.
    docs/
        index.md  # The documentation homepage.
        ...       # Other markdown pages, images and other files.

### A code block

    A whole bunch of lines
    of code that should automatically
    be rendered correctly