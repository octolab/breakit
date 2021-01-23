> # ⏲ breakit
>
> Flexible mechanism to execute commands for a limited time.

[![Build][build.icon]][build.page]
[![Documentation][docs.icon]][docs.page]
[![Quality][quality.icon]][quality.page]
[![Template][template.icon]][template.page]
[![Coverage][coverage.icon]][coverage.page]
[![Mirror][mirror.icon]][mirror.page]

## 💡 Idea

```bash
$ date
# Thu Jan  7 21:02:21
$ breakit after 10m -- server run --port=8080
$ breakit ps
# +--------------------------+----------------------------+----------+----------+
# | Process                  | Status                     | Since    | Until    |
# +--------------------------+----------------------------+----------+----------+
# | server run --port=8080   | exit 1; panic: database... | 21:02:36 | -        |
# +--------------------------+----------------------------+----------+----------+
# |                          |                            |    Total |        1 |
# +--------------------------+----------------------------+----------+----------+
$ breakit after 10m -- database run --port=5432
$ breakit after 10m delay 5s -- server run --port=8080
$ breakit ps
# +--------------------------+----------------------------+----------+----------+
# | Process                  | Status                     | Since    | Until    |
# +--------------------------+----------------------------+----------+----------+
# | database run --port=5432 | running                    | 21:04:09 | 21:14:09 |
# | server run --port=8080   | delayed                    | 21:04:30 | 21:14:25 |
# +--------------------------+----------------------------+----------+----------+
# |                          |                            |    Total |        2 |
# +--------------------------+----------------------------+----------+----------+
```

A full description of the idea is available [here][design.page].

## 🏆 Motivation

...

## 🤼‍♂️ How to

...

## 🧩 Installation

### Homebrew

```bash
$ brew install octolab/tap/breakit
```

### Binary

```bash
$ curl -sSfL https://raw.githubusercontent.com/octolab/breakit/master/bin/install | sh
# or
$ wget -qO-  https://raw.githubusercontent.com/octolab/breakit/master/bin/install | sh
```

> Don't forget about [security](https://www.idontplaydarts.com/2016/04/detecting-curl-pipe-bash-server-side/).

### Source

```bash
# use standard go tools
$ go get go.octolab.org/toolset/breakit@latest
# or use egg tool
$ egg tools add go.octolab.org/toolset/breakit@latest
```

> [egg][] is an `extended go get`.

### Shell completions

```bash
$ breakit completion > /path/to/completions/...
# or
$ source <(breakit completion)
```

<p align="right">made with ❤️ for everyone</p>

[awesome.icon]:     https://awesome.re/mentioned-badge.svg
[build.page]:       https://travis-ci.com/octolab/breakit
[build.icon]:       https://travis-ci.com/octolab/breakit.svg?branch=master
[coverage.page]:    https://codeclimate.com/github/octolab/breakit/test_coverage
[coverage.icon]:    https://api.codeclimate.com/v1/badges/c570179a9335c747e77c/test_coverage
[design.page]:      https://www.notion.so/33715348cc114ea79dd350a25d16e0b0?r=0b753cbf767346f5a6fd51194829a2f3
[docs.page]:        https://pkg.go.dev/go.octolab.org/toolset/breakit
[docs.icon]:        https://img.shields.io/badge/docs-pkg.go.dev-blue
[mirror.page]:      https://bitbucket.org/kamilsk/breakit
[mirror.icon]:      https://img.shields.io/badge/mirror-bitbucket-blue
[promo.page]:       https://github.com/octolab/breakit
[quality.page]:     https://goreportcard.com/report/go.octolab.org/toolset/breakit
[quality.icon]:     https://goreportcard.com/badge/go.octolab.org/toolset/breakit
[template.page]:    https://github.com/octomation/go-tool
[template.icon]:    https://img.shields.io/badge/template-go--tool-blue

[_]:                https://img.shields.io/sourcegraph/rrc/go.octolab.org/toolset/breakit
[egg]:              https://github.com/kamilsk/egg
