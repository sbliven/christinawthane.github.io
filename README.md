# LilyBee

Source for http://lilybee.ch. The site is hosted on [github](https://github.com/christinawthane/christinawthane.github.io/). A beta site can be accessed at https://sbliven.github.io


# Organization

Where possible, content has been written in Markdown for easy editing. This gets combined with jekyll templates to build the page in a consistent style.

Simple pages are added to the root directory as HTML or Markdown files (e.g. about.md). 

Multi-section pages (`/signingtime` and `/babywearing`) are generated from directories of markdown files (e.g. `_signingtime` and `_babywearing`). The babywearing content is localized to English and German based on the `language` property in the YML header.

The `_data` directory holds some configuration that gets used on multiple pages: the global nav bar, and the list of current courses, and prices for courses.


# Building locally

The site is generated using jekyll and markdown. This happens automatically on github. Building locally requires ruby.

```
gem install jekyll bundler
```

Install dependencies:

```
bundle
```

Start a local development server with

```
bundle exec jekyll serve
```


# Frameworks

- Jekyll 3.6.2
    - Ruby 2.4.2
    - Only github-pages plugins
- Bootstrap 4.0.0
  - jQuery 3.3.1
  - Popper 1.12.9


# Tips

**Links**

Use jekyll to generate the right path for a link: `{{site.baseurl}}{% link path/to/file.md %}`. This allows the path to change if the permalink for the page gets updated, and throws an error if the link is broken.

```
Markdown, resolves to /babywearing:
[Babywearing]({{site.baseurl}}{% link babywearing/index.html %})

<p>HTML, resolves to /about:</p>
<a href="{{site.baseurl}}{% link about.md %}">About</a>
```
