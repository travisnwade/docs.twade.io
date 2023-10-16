# Travis Wade Documentation Wiki

## How this site got started

Basically, I was just fucking around.  I wanted a quick and easy Wiki style site that I could use as a personal reference to
common tasks I do or things that took me a bit of troubleshooting to figure it out. Then I wanted to document it.

I also didn't want to spend much money on it.  (Free if possible).  And I found MKDocs. Needs a bit of setup locally,
but essently write your docs in markdown, then run a simple `mkdocs build` command to compile static HTML into a `site` directory
which can then be published directly to Netlify's CDN.  Free, easy SSL, and minimal overhead.  All of which I fucking love.

### MKDocs
For full documentation visit [mkdocs.org](https://www.mkdocs.org).

## Where I host this
### [Netlify](/netlify/)
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