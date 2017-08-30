# .meta-project

The project, [sublime-settings], is a collection of the files that comprise my
Sublime 3 Configuration.

[sublime-settings]: https://github.com/jedcn/sublime-settings

*This directory* contains files that manage the configuration, but *aren't
used* by Sublime 3 itself.

Some of these files are stored both in a bare config file and a corresponding
markdown file with [there-and-back-again].

[there-and-back-again]: https://github.com/jedcn/there-and-back-again

This NPM based functionality is made possible with a [package.json] and
[some shell scripts].

[package.json]: ./package.json
[some shell scripts]: ./bin

Lastly, there's a pair of functions that allow you to type:

* `update`: Update markdown files from changed config files
* `extract`: Extract config files from changed markdown files

## Getting Started

You can define `update` and `extract` by running the following command from the
root of this [project][sublime-settings].

```shell
source .meta-project/source.me
```

Once you've run this command, you can run `update` or `extract` from wherever
you'd like-- they know to come back to this project before they run.
