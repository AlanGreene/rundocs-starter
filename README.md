# Runbooks

## Install

To run locally:

```sh
bundle install
bundle exec jekyll serve --livereload
```

It will automatically reload your browser whenever you save a change in the markdown files.
If you make a change to `_config.yaml` you will need to restart the `jekyll serve` command.

If this is a new project you will also need to initialise a git repo before it will run as some of the plugins require access to git metadata.

```sh
git init
git remote add origin <url>
```

## _config.yaml
- set `title`, `description`, and `author`
- `copyright` controls the content of the page footer
  - set `copyright.revision` to `false` to hide the git revision
  - set `copyright: false` to hide the footer entirely
- set `edit: false` to hide the link to edit the current page on GitHub (icon on top right of page)

## Generate TOC

Add a `README.md` to each folder you want to include in the navigation.

The first line of each markdown file (whether a content page or a folder README) should be a H1 tag with the title of the page / folder, e.g.
```
# My Page
```

This will be used to generate the displayed name for links in the navigation.

If you omit the title the path will be used instead, see `/category-a/test2.html` in the nav for example.

To control the sort order, add YAML frontmatter with the `sort` field specifying the numeric order, e.g.:
```
---
sort: 1
---

# My Page
```



### List all pages in current folder

{% raw %}
```
{% include list.liquid %}
```
{% endraw %}

That will generate a list like this:
{% include list.liquid %}

### List all pages and sub folders in the current folder

{% raw %}
```
{% include list.liquid all=true %}
```
{% endraw %}

That will generate a list like this:
{% include list.liquid all=true %}

...


## Custom styles

Add custom styles in `_includes/assets/custom.scss`

## Custom scripts

Add custom JavaScript in `_includes/assets/custom.js`
