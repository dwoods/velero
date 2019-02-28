---
permalink: /
redirect_to:
- LATEST
---

# Velero - Docs Branch

This special branch (`gh-pages`) is used to generate the [public documentation site](https://heptio.github.io/velero)
for velero. This site is hosted using [Github Pages](https://help.github.com/articles/what-is-github-pages/).

The content files in this branch were generated with a tool that Heptio builds and maintains. This means that if you change docs content in this branch to fix something on the docs site, make sure to change the equivalent content in the docs directory on the master branch.

## View the site

    In the root of the  project...

    Run: `make serve`

    Open http://0.0.0.0:4000/velero/

## Test the site

To test the site's docs for valid links and proper style, run the following in the root of the project:

```
make all-test
```

All test output files are written to the `./logs` directory (which is already in the `.gitignore`):
* `link-check.log` - *[Checks the generated HTML]* Are links valid?

* `style-check.log` - *[Checks the markdown source on `master`]* Are common documentation conventions followed?

* `site-build.log` - Can the markdown source be properly converted into the HTML site? (The build output is used in the link checking test).

Note: running `make clean` will delete the `logs` directory.

## Where to make changes

Where should changes go, given that there are files being pulled in from several different locations?

* **Version-specific changes**
    * *Ex:* fixing a typo or adding an image
    * Checkout the `gh-pages` branch
    * Make the change in the relevant directory/files
    * Create PR against the `gh-pages` branch.

* **Project-specific changes**
  * *Ex:* TOC changes
  * Same as above, these changes should be made as PRs to the `gh-pages`. branch, so that they apply across all versions.