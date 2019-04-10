# git-fancy
Git hook that emojifies your commit messages with project-defined emoji
codes. Since it's just a
[commit-msg hook](https://git-scm.com/docs/githooks#_commit_msg), you
can use any tool to compose your emoji-charged commit messages, and
since each emoji code gets translated to Unicode, your commit messages
will look great in any Unicode-aware environment.

## Installation
Copy [commit-msg](commit-msg) to your hooks directory (by default, the
`.git/hooks` directory of a repository).

## Configuration
You define a project's emoji codes via a `.fancyconfig` file located at
the root of a Git repository. The format of `.fancyconfig` is the same
as that of a
[Git configuration file](https://www.git-scm.com/docs/git-config#_configuration_file).
Its sole section is `[emoji]` and contains definitions of custom emoji
codes in the format of *emojicode = emoji*, where *emojicode* is a
sequence of supported ASCII characters (letters, numbers, `_`, `+`, and
`-`) and *emoji* a sequence of Unicode characters. For example,
`fix = 🐛` defines the emoji code `fix` that can be used to easily add
`🐛` to a commit message.

See [.fancyconfig](.fancyconfig) of this repository for an example
configuration.
