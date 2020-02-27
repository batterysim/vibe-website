# VIBE website

This repository contains files for the VIBE website which is published at [vibe.ornl.gov](https://vibe.ornl.gov).

The site can also be viewed at [batterysim.github.io/vibe-website/](https://batterysim.github.io/vibe-website/). This url is the GitHub Pages version which is used for development purposes.

The website is generated with [Jekyll](https://jekyllrb.com) and uses the [pages-gem](https://github.com/github/pages-gem) to ensure compatibility with hosting on GitHub Pages. For information on building the site locally, see this [article](https://help.github.com/en/articles/testing-your-github-pages-site-locally-with-jekyll).

## Examples

VIBE examples are displayed on the homepage. Each example is represented as a markdown file in the `_examples` folder. The front matter block in the markdown file must contain the `name`, `image`, and `link` for the example. The paragraph content of the markdown file is a brief description of the example.

## Updating

If you build this website locally, make sure Bundler and the GitHub Pages gem are updated to the latest versions by using the following commands:

```bash
# Update the Ruby Bundler gem
$ gem update bundler

# Update the GitHub Pages gem
$ bundle update github-pages
```
