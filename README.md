# ITK Development scripts

Useful scripts for daily life and work as ITK Development.

## Installation

Clone [this repository](https://github.com/itk-dev/itk-scripts) and add the [`scripts`](scripts/) folder to your path.

If you're running [Zsh](https://www.zsh.org/), run

``` zsh
echo 'export PATH="'$(git rev-parse --show-toplevel)/scripts':$PATH"' >> ~/.zshrc
```

to add the script to your PATH. If you're [still
using](https://www.howtogeek.com/362409/what-is-zsh-and-why-should-you-use-it-instead-of-bash/)
[Bash](https://www.gnu.org/software/bash/), run

``` bash
echo 'export PATH="'$(git rev-parse --show-toplevel)/scripts':$PATH"' >> ~/.bashrc
```

Check that everythin work by opening a new terminal and running [one of the scripts](#scripts).

## Scripts

| Script        | Description                     |
|---------------|---------------------------------|

## Coding standards

``` shell name=coding-standards-shell
docker run --rm --tty --volume "$PWD:/app" --workdir /app peterdavehello/shellcheck shellcheck scripts/*
```

``` shell name=coding-standards-markdown
docker run --rm --volume "$PWD:/md" peterdavehello/markdownlint markdownlint --ignore LICENSE.md --ignore vendor/ --ignore node_modules/ '**/*.md' --fix
docker run --rm --volume "$PWD:/md" peterdavehello/markdownlint markdownlint --ignore LICENSE.md --ignore vendor/ --ignore node_modules/ '**/*.md'
```

Pro tip: Use
[`markdown-code-runner`](https://github.com/mikkelricky/markdown-code-runner?tab=readme-ov-file#markdown-code-runner) to
run the code snippets above, e.g.

``` shell
markdown-code-runner run coding-standards-markdown
```
