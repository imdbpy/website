The site uses the [Lektor](https://www.getlektor.com/) static site generator.

## Installation

Install lektor:

```
pip install lektor
```

- Start the live development server:

  ```
  lektor server -f gulp -O _build
  ```

- Browse to the reported URL.

- Edit the files and see the results in the browser.
  Don't use the admin panel (the pencil button) if you're not
  familiar with lektor.

- When you're done, push your changes and Travis will automatically
  build and deploy the site.

  If you don't want to trigger a deployment to the live site,
  include the text `[skip ci]` on a separate line in the commit message.

- To build or deploy manually, run the commands:

  ```
  lektor build -f gulp -O _build
  lektor deploy ghpages -O _build
  ```

## Content

The site content is under the `content` directory.
There is one directory per page.
The content of the page is placed into the `contents.lr` file
in the corresponding directory.

News items have to be placed into the `news` directory.
Just copy an existing news item directory and
edit the `contents.lr` file of the new item.

The `ecosystem` page consists of `project` elements.
To add a new project, copy an existing project and
edit the `contents.lr` file.

## Style

The site uses a customized version of the [Bulma](https://bulma.io/)
framework.
The variables to set and the style overrides are
in the `theme/sass` directory.
Do not edit the CSS files under `theme/css` and `assets/static`
since these will be generated by the build process.

## Content Modeling

Fields of content types (like news items and projects) are stored
in `.ini` files under the `models` directory.

For each content type, there has to be a template
under the `templates` directory.

Templates can use data stored in `.json` files under the `databags` directory.
