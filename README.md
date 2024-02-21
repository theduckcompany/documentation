# Duckcloud: Official Documentation (English) #

[![Documentation](https://img.shields.io/badge/read-the%20docs-4aa087.svg)][docs]
![Matrix](https://img.shields.io/matrix/duckcloud%3Amatrix.org)

These source files are written in [human-friendly Markdown](https://squidfunk.github.io/mkdocs-material/reference/). They are meant to be parsed with [MkDocs Material](https://squidfunk.github.io/mkdocs-material/) to generate the final HTML pages published at [docs.duckcloud.fr](https://docs.duckcloud.fr/).

Although arguably less convenient to work with than a Wiki, this enables us to easily merge pull requests and constantly improve our documentation in a transparent way.
Direct access to the source files in a revision control system is a big plus to ensure the quality of our documentation.

## Editing Content ##

At the top of each generated page is an *edit this page* link to the corresponding page on GitHub, where you can make changes (and submit pull requests with a few clicks) without needing to know Git or run anything on your system.

To make more extensive changes, fork this repository, modify the corresponding `.md` source files (or create new ones), commit the changes, push them back to your fork, and then submit a pull request to our `master` branch.

### Project Layout ###

```text
mkdocs.yml    # The configuration file.
docs/
    index.md  # The documentation homepage.
    ...       # Other markdown pages, images and other files.
```

[docs]: https://docs.duckcloud.fr/
