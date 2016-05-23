Licenses html generator
=======================

[ ![npm](https://img.shields.io/npm/v/licenses-html-generator.svg) ](https://www.npmjs.com/package/licenses-html-generator)

Generates an html licenses file from a list of license sources, which can be git repos or local files. For git repos, it makes a shallow clone and automatically gets the license from the readme or license file.

[Example sources file](http://stephentuso.github.io/licenses-html-generator/sources.json)

[Example generated page](http://stephentuso.github.io/licenses-html-generator/licenses.html)

Usage
-----

1) Install with `npm install -g licenses-html-generator`

2) Create a new directory for the script to do its thing in (this is where it will clone any git repos and where the output html file will be)

3) In that directory, create a file called `sources.json` that contains a json array of sources:

```
[
    {
        "name": "Example 1",
        "uri": "https://github.com/example/example-repo.git"
    },
    {
        "name": "Example 2",
        "uri": "./local-license-text-file.txt"
    }
]

```

4) Run `licenses-html-generator /path/to/dir/from/step/2`. The html file will be located at `./out/licenses.html`

Templates
---------

The output can be customized by adding a folder called `templates` to the directory containing `sources.json` and adding any of the following files:

`head.html` - Contents for the `head` tag

`styles.css` - CSS that will be inlined. Use `.license` to style the licenses. This is added in addition to the default styles. To override the default styles use `default-styles.css`

`header.html` - Html to go at top of page, above all licenses. Will be contained in a `header` element.

`license-header.html` - Html that comes before each license. Put `<!--NAME-->` where you want the name of the license to go.

`license.html` - For wrapping the license html. Put `<!--LICENSE-->` where you want the license html to go.

`footer.html` - Html for the bottom of the page. Will be contained in a `footer` element. If you don't want to have "Created with Licenses HTML Generator" at the bottom, create this file.

License
-------

Released under the MIT License.
