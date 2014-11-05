Gitbook-Style-Rewrite
==============

This is a sample plugin for GitBook.

## How GitBook plugin works?

### package.json

#### name

The package name should begin with ```gitbook-plugin-```. And if your plugin is a theme, it should begin with ```gitbook-theme-```.

#### engine

The package.json should contain a `engine` field using [the standard norm](https://www.npmjs.org/doc/json.html#engines).

```
"engines": {
    "gitbook": "*"
}
```

### entry point

The plugin entry point should return an object with some metadata.

#### "book"

Type: `Object`
Default value: `{}`

#### "book.assets"

Type: `String`
Default value: `null`

Path to the assets folder to copy

#### "book.js"

Type: `Array`
Default value: `[]`

List of javascript file to add to the html pages (relative to the assets fodler).

#### "book.css"

Type: `Array`
Default value: `[]`

List of css file to add to the html pages (relative to the assets fodler).

#### "book.templates"

Type: `Object`
Default value: `{}`

Templates to override default templates, only use this option if you want to change entirely how the book is rendered.

This object is a map: "name" -> "file", with names:

* "site": page for a file from the `site` format
* "page": page for the `page` format

#### "hooks"

Type: `Object`
Default value: `{}`

Map of "name" -> Function that needs to be called during build process. With names:

* "init": just after initialization, before generation
* "finish": after generation and everything is finished

Each hook can return a promise.

