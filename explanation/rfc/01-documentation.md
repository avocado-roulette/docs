# RFC 1: Documentation framework

| Author | Approver(s) |
| --- | --- |
| Dan Miller | Dipankar Ray |

## Introduction

This repo
[recommends using Diátaxis](https://github.com/avocado-roulette/docs/blob/main/README.md)
to organize the docs. However, [Diátaxis](https://diataxis.fr/) is a
"systematic approach to technical documentation authoring", not an actual framework or
hosting mechanism. This
[RFC (**R**equest **F**or **C**omment)](https://en.wikipedia.org/wiki/Request_for_Comments)
proposes a specific combination of documentation framework and hosting platform to use
for any future documentation we write.

## Proposal

There are two components of a good documentation site:

1. The framework used to _write and render_ docs
2. The platform used to _host the rendered docs_

The former will control the "look and feel" of the docs, along with any customization
/ extensibility, the latter will control their domain, as well as possibly constrain
the choice of framework (e.g. between static / non-static options).

I recommend we use a combination of
[MkDocs](https://www.mkdocs.org/) with the
[Material for MkDocs](https://squidfunk.github.io/mkdocs-material/) extension for
a framework, and
[Read the Docs](https://docs.readthedocs.com/platform/stable/index.html)
as the hosting platform.

Example: "Ptah", a personal side project of the author's.

- Site: [ptah.readthedocs.io](https://ptah.readthedocs.io)
- Configuration: [ptah / mkdocs.yml](https://github.com/dkmiller/ptah/blob/main/mkdocs.yml)
- CI/CD: [readthedocs.yml](https://github.com/dkmiller/ptah/blob/main/.github/workflows/readthedocs.yml)

Read the Docs supports easy credential-less CI/CD and docs "preview" generated from
pull requests. For this project, it would result in a domain like below.

> `avocado-roulette.readthedocs.io`

The MkDocs framework has a very rich extension ecosystem, and is easy to configure
via the "Material for MkDocs" extension, without needing frontend expertise.

## Alternatives

This section lists alternatives we considered for rendering framework and hosting
platform.

## [GitHub Pages](https://docs.github.com/en/pages)

Examples:

- https://microsoft.github.io/presidio/

Cons: does not support automatic pull request preview, is
[trickier to publish to the root of a domain](https://docs.github.com/en/pages/getting-started-with-github-pages/what-is-github-pages#user-and-organization-pages-sites).

## [Docusaurus](https://docusaurus.io/)

Examples:

- https://docs.litellm.ai/

Docusaurus is _very_ powerful and looks slightly better than MkDocs, but requires more
frontend expertise to fully leverage.
