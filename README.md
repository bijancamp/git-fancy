# git-fancy
Git hook that emojifies your commit messages with project-defined emoji
codes. Since it's just a [commit-msg hook], you can use any tool to
compose your emoji-charged commit messages, and since each emoji code
gets translated to Unicode, your commit messages will look great in any
Unicode-aware environment.

<img src="docs/images/demo.gif" alt="Demo of git-fancy" width="641">

<!-- Links -->
[commit-msg hook]: https://git-scm.com/docs/githooks#_commit_msg


## Installation
git-fancy requires Python 3.6+ and the following setup:
1. Copy [commit-msg] to your hooks directory (by default, the
`.git/hooks` directory of your repository).
2. Ensure you have adequate permissions to execute `commit-msg`.
3. Add a `.fancyconfig` file at the root of your repository containing
definitions of emoji codes as described in [Configuration].

<!-- Links -->
[commit-msg]: commit-msg
[Configuration]: #configuration


## Configuration
You define a project's emoji codes via a `.fancyconfig` file located at
the root of the repository.

The format of `.fancyconfig` is the same as that of a [Git configuration
file]. Its sole section is `[emoji]` and contains definitions of custom
emoji codes in the format of *emojicode = emoji*, where *emojicode* is a
valid sequence of ASCII characters (begins with a letter with subsequent
characters being letters, numbers or hyphens) and *emoji* a sequence of
Unicode characters. For example, `fix = 🐛` defines the emoji code `fix`
that can be used to easily add `🐛` to a commit message.

See [.fancyconfig] of this repository for an example configuration.

<!-- Links -->
[Git configuration file]: https://www.git-scm.com/docs/git-config#_configuration_file
[.fancyconfig]: .fancyconfig


## Usage
To use custom emoji codes in your commit messages, type `:emojicode:` in
a commit message, where `emojicode` is the name of one of the variables
[you've defined]. For example, if you've defined the emoji code `style`
to be `💎`, then you can type
```
:style: Rename function
```
to use
```
💎 Rename function
```
as the commit message.

You can write your emoji-coded commit messages from the command line or
your favorite editor!

<!-- Links -->
[you've defined]: #configuration
