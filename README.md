# irbrc

[![Ruby CI](https://github.com/kachick/irbrc/actions/workflows/ruby.yml/badge.svg?branch=main)](https://github.com/kachick/irbrc/actions/workflows/ruby.yml?query=branch%3Amain+)

Extracted from https://github.com/kachick/dotfiles because of it is only one of depending ruby environment

## Installation

```bash
cd "$(mktemp --directory)"
curl -OL https://raw.githubusercontent.com/kachick/irbrc/main/.irbrc
mv ./.irbrc ~/
curl -OL https://raw.githubusercontent.com/kachick/irbrc/main/Gemfile
bundle config set path.system true
BUNDLE_WITHOUT='development:test' bundle install
```

It may require some core dependencies like gcc.\
For example building io-console native gem errors, you should try.

```bash
# Download as above
# And inject gcc for the PATH with impure mode
nix-shell --packages gcc
BUNDLE_WITHOUT='development:test' bundle install
```

Then you can use irb as follows

```console
/tmp/tmp.hutvKLSLVC via 💎 v3.3.0 22s zsh
> irb
irb(main):001> pa (2 * 3 * 7).abs == 1010102.to_s.to_i(2)
(2 * 3 * 7).abs == 1010102.to_s.to_i(2)
            |   |          |    |
            |   |          |    42
            |   |          "1010102"
            |   true
            42

=> true
=> nil
```
