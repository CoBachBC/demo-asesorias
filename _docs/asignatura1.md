---
title: Asignatura 1
tags: 
 - mate
---

# Asignatura 1

## Tema 1

### Explicación

If you look at any header field on the page, you'll notice three little dots 
(called an elipsis) that if you mouse over, will open up to give you options
for Permalink, Edit this Page, and Ask a Question. 
These are to ensure that a user is able to link someone else directly to a section
of interest (Permalink), contribute a fix or suggestion to the documentation itself on GitHub
(Edit this page) or open up an issue that links directly to where the user has
the question. Documentation is hard, and sometimes unclear, and the site
should make it easy to ask a question or suggest a change.

### Ejemplos

The entire site, including posts and documentation, is indexed and then available
for search at the top of the page. Give it a try! The content is rendered
from [this file](https://github.com/vsoch/mkdocs-jekyll/blob/master/search/search_index.json)
into [this json data structure](https://vsoch.github.io/mkdocs-jekyll/search/search_index.json)
that feeds into the search defined in `assets/js/application.js`. If you want to
exclude any file from search, add this to its front end matter:

```
---
layout: null
excluded_in_search: true
---
```

The example above is for a css file in the assets folder that is used as a template, but should not be included in search. If you need to disable search entirely for a page, you can add the `disable_search` header:

```
---
layout: null
disable_search: true
---
```

Disabling search will remove the search box at the top.

### Cuestionario

{% include quiz.html file='asignatura1-tema1' %}

## Tema 2

Initially (on OS X), you will need to setup [Brew](http://brew.sh/) which is a package manager for OS X and [Git](https://git-scm.com/). To install Brew and Git, run the following commands:

```bash
/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
brew install git
```

If you are on Debian/Ubuntu, then you can easily install git with `apt-get`

```bash
apt-get update && apt-get install -y git
```

### Explicación

You can also install Jekyll with brew.

```bash
$ brew install ruby
$ gem install jekyll
$ gem install bundler
$ bundle install
```

On Ubuntu I do a different method:

```bash
git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc
exec $SHELL
rbenv install 2.3.1
rbenv global 2.3.1
gem install bundler
rbenv rehash
ruby -v

# Rails
curl -sL https://deb.nodesource.com/setup_4.x | sudo -E bash -
sudo apt-get install -y nodejs
gem install rails -v 4.2.6
rbenv rehash

# Jekyll
gem install jekyll
gem install github-pages
gem install jekyll-sass-converter

rbenv rehash
```

### Ejemplos

You should first fork the repository to your GitHub organization or username,
and then clone it.

```bash
$ git clone https://github.com/<username</mkdocs-jekyll.git docs
$ cd docs
```

You can clone the repository right to where you want to host the docs:

```bash
$ git clone https://github.com/<username>/mkdocs-jekyll.git docs
$ cd docs
```

## Tema 3

### Explicación

To edit configuration values, customize the [_config.yml](_config.yml).
Most are documented there, and please [open an issue](https://www.github.com/{{ site.github_user }}/{{ site.github_user }}/issues) if you have questions.

### Ejemplos

To add pages, write them into the [pages](pages) folder. 
You define urls based on the `permalink` attribute in your pages,
and then add them to the navigation by adding to the content of [_data/toc.yml](_data/toc.yml).