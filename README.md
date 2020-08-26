# Website

This repository contains the [Hugo][hugo] site and generator scripts for my website. In the future, the site will be available at https://rothandrew.com. For now, you can access the in-progress site at https://rothandrewdocsy.netlify.app.

Lifted from https://github.com/kubernetes-sigs/contributor-site and modified for my own use.

## Running the site locally

To develop site content, you can run the site locally using [Hugo][hugo] in two ways:

1. [Website](#website)
   1. [Running the site locally](#running-the-site-locally)
      1. [Using Docker](#using-docker)
      1. [Natively](#natively)

When you make changes to the site's content, Hugo will automatically update the site and refresh your browser window.

### Using Docker

The easiest and most cross-system-compatible way to run the site is to use [Docker][docker]. To begin, create the docker image to be used with generating the site by executing `make docker-image`.

To ensure you can view the site with externally sourced content, run `make docker-gen-content` before previewing the site by with `make docker-server`.

### Natively

For instructions on installing and using Hugo, see the [Hugo Documentation][hugo-docs].
Note that the extended version is required.

In addition to Hugo, the [postcss-cli] and [autoprefixer] JavaScript packages are
required. These can be installed via the [Node Package Manager] (`npm`) from a
recent version of [nodejs] with `npm install -g postcss-cli autoprefixer`.

The Contributor Site uses the [docsy] theme. It is included as a [git submodule].
To fetch docsy and it's requirements, run the command:

```
git submodule update --init --recursive --depth 1
```

To ensure you can view the site with externally sourced content, run `make gen-content` before previewing the site by with `make server`.

**NOTE to OSX Users**

 The `hack/gen-content.sh` script requires the gnu version
of base packages such as `find`, `grep`, and `sed`. 

```
brew install coreutils findutils grep gnu-sed gnu-tar make readlink
```

You will then need to update your path to include these:

```
export PATH="/usr/local/opt/coreutils/libexec/gnubin:$PATH"
```

[hugo]: https://gohugo.io/
[Markdown]: https://www.markdownguide.org/
[ct]: ./content/
[pr]: https://help.github.com/en/articles/about-pull-requests
[hugo-docs]: https://gohugo.io/getting-started/installing
[frontmatter]: https://gohugo.io/content-management/front-matter/
[docker]: https://www.docker.com/get-started
[sig-contribex]: https://github.com/kubernetes/community/blob/master/sig-contributor-experience/README.md
[sig-contribex-slack]: http://slack.k8s.io/#sig-contribex
[sig-contribex-list]: https://groups.google.com/forum/#!forum/kubernetes-sig-contribex
[kep-0005]: https://github.com/kubernetes/enhancements/blob/master/keps/sig-contributor-experience/0005-contributor-site.md
[docsy]: https://docsy.dev
[postcss-cli]: https://postcss.org/
[autoprefixer]: https://github.com/postcss/autoprefixer
[git submodule]: https://git-scm.com/book/en/v2/Git-Tools-Submodules
