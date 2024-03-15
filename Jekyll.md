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