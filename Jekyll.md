# Jekyll Tutorial

## What is Jekyll?

- Jekyll is a simple, blog-aware, static site generator.
- It is easy to set up and use, making it accessible to both beginners and experienced developers.
- Jekyll allows you to write your content in Markdown, a lightweight markup language that is easy to read and write.
- It has built-in support for templates, allowing you to create consistent layouts for your site.
- Jekyll automatically generates a static HTML site, which means your site will load quickly and be more secure.

## How to use Jekyll?

Jekyll is written in Ruby. To get started, you'll need Ruby and Ruby on Rails.
- Ruby on Rails: https://rubyonrails.org

- Jekyll: https://jekyllrb.com

- Install Jekyll: `gem install jekyll`
- Create a new Jekyll project: `jekyll new my-project`
- Run Jekyll: `bundle exec jekyll serve`
or
- Run Jekyll: `jekyll serve`

## Front Matter

- Front Matter: https://jekyllrb.com/docs/front-matter/
- Front Matter: https://jekyllrb.com/docs/configuration/front-matter

- it is used to add metadata to your Jekyll site, such as author, title, and date.
- can be written in YAML or JSON format (key-value pair constructs).
- can be customized to suit your needs.

example:

```yaml
---
layout: post
title:  "Welcome to Jekyll!"
date:   2024-03-15 21:58:54 +0000
categories: jekyll update
---
```

## Jekyll Posts

- post filenames follow the `YYYY-MM-DD-name.extension` format

## Drafts

- Drafts: https://jekyllrb.com/docs/drafts
- you need to create a directory `_drafts` in your Jekyll project
- add your draft to the `_drafts` directory by adding `filename.md`
- run `jekyll serve --drafts` to see your draft
- if you move the file to `_posts`, it will be published, but you need to name it with the `YYYY-MM-DD-name.extension` format

## Creating Pages

- Pages: https://jekyllrb.com/docs/pages
- Pages on the website that aren't posts or drafts are pages. Pages are used to add additional content to your site, such as blog posts, project pages, and other content that you want to share with your readers.
- they are markdown files in the root of the project
- you just need to add front matter and content to your page.

## Permalinks

- Permalinks: https://jekyllrb.com/docs/permalinks
- Permalinks are used to create URLs for your posts, pages, and other content.
- frontmatter key `permalink` is used to set the permalink

example:

```yaml
---
layout: post
title:  "Welcome to Jekyll!"
date:   2024-03-15 21:58:54 +0000
categories: jekyll update
permalink: /my-permalink
---
```

- permalink can be used with variables to create dynamic URLs.
- can be set to `:title` or `:year/:month/:day/:title`
- can be set to `:slug` or `:year/:month/:day/:slug`
- can be set to `:id` or `:year/:month/:day/:id`
- can be set to `:categories` or `:year/:month/:day/:categories`
- even with custom extensions, you can set it to `:title.html` or `:year/:month/:day/:title.html`


## Jekyll Tutorials

- Jekyll Tutorials: https://jekyllrb.com/tutorials
- Jekyll Tutorials are a series of Jekyll tutorials that cover different aspects of Jekyll. They are meant to help you get started with Jekyll.
- Jekyll Tutorials are written in Markdown and can be created in any text editor.
- Jekyll Tutorials are organized into categories, such as "Getting Started" or "Advanced".

## Front Matter Defaults

- Front Matter Defaults: https://jekyllrb.com/docs/front-matter-defaults
- Front Matter Defaults are used to set default values for front matter in Jekyll.

- we can do that by adding the following to your `_config.yml` file:
  - defaults variable: `defaults: [page]`

  ```yaml
  defaults:
  -
    scope:
      path: ""
      type: "post"
    values:
      layout: "post"
  ```

- `defaults` variable is an array of objects, each object represents a default value for a specific front matter key.
- `scope` variable is used to set the scope of the default value.
- `values` variable is used to set the values of the default value.
- `layout` variable is used to set the layout of the default value.
- `path` variable is used to set the path of the default value.
- `type` variable is used to set the type of the default value.

- whenever you change -config.yml, you need to restart your server.

- because we defined defaults variable in `_config.yml`, we don't need to specify front matter at the beginning of each post.

## Themes

- Themes: https://jekyllrb.com/docs/themes
- Themes are used to customize the look and feel of your Jekyll site.
- Themes are written in Sass and can be created in any text editor.
- Themes are organized into categories, such as "Minimal" or "Modern".

- default theme is `minima`
- you can change the default theme in `_config.yml`
- find a theme that you want to use: https://rubygems.org 
- go to `Homepage` for more information (usually GitHub repository) and you can see the preview of the theme
- you go to `Gemfile` and add the theme: `gem 'jekyll-theme-hacker'`
- then go to the terminall and run `bundle install`
- run it again `bundle exec jekyll serve`

- there will be errors - missing layouts if the theme doesn't have these - we can see on the GitHub which layouts the theme has


## Layouts

- Layouts: https://jekyllrb.com/docs/layouts
- theme is defining the layout for each page
- can be overridden:
  - we make a folder `_layouts` in the root of the project
  - inside we place the layout as html file
  - once you make the layout file, you use the variables to get the content of the page
  - `{{ content }}` - placeholder for all of the content of the page
- the name of the layout is the name of the html file in the `_layouts` folder

- you can also define different levels of layouts
- high level layout - that all the pages are using
- low level layout - that specific page is using

example high level (`wrapper.html`):

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <title>Document</title>
</head>
<body>
    Wrapper
    <br>
    {{ content }}
    <br>
    Wrapper
</body>
</html>
```

example of low level:
```html
---
layout: wrapper
---
<h1>This is a post</h1>

<hr>

{{ content }}
```