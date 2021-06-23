# [PDF.js](https://github.com/mozilla/pdf.js) for [NexT](https://github.com/next-theme/hexo-theme-next)

## Introduce

This is a plugin that allows to preview PDF files in the blog pages.

If the browser supports embedded PDFs natively, NexT will create a `<embed>` tag and include the PDF file on your website. Otherwise it will create a `<iframe>` tag and uses PDF.js by @mozilla to render the pdf file.

Follow the guide below to install dependencies.

## Installation

### Step 1 &rarr; Go to Hexo dir

Change dir to **Hexo** directory. There must be `source`, `themes` and other directories:

```sh
$ cd hexo-site
$ ls
_config.next.yml  db.json           package-lock.json scaffolds         themes
_config.yml       node_modules      package.json      source
```

### Step 2 &rarr; Get module

Install module to `source/lib` directory:

```sh
$ git clone https://github.com/next-theme/theme-next-pdf source/lib/pdf
```

### Step 3 &rarr; Set it up

Enable module in **NexT** `_config.next.yml` file:

```yml
# PDF tag
# NexT will try to load pdf files natively, if failed, pdf.js will be used.
# So, you have to install the dependency of pdf.js if you want to use pdf tag and make it available to all browsers.
# See: https://github.com/next-theme/theme-next-pdf
pdf:
  enable: true
  # Default height
  height: 500px
```

Find and edit `skip_render` settings in **Hexo** `_config.yml` file:

```yml
skip_render:
  - lib/**/*
```

## Usage

In order to embed PDF files in the article, you just need to create an `pdf` tag with the URL of your local PDF file, e.g.

```
{% pdf /path/to/your/file.pdf %}
```
Notice: Do not use cross-origin PDF files, it might be blocked by the CORS policy.

Enjoy it!

## Update

```sh
$ cd hexo-site/source/lib/pdf
$ git pull
```
