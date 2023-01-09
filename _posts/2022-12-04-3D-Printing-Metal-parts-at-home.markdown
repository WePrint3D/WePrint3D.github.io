---
layout: post
title: The begining of a new era for 3D printing
description: How would we be able to 3d print metal parts at home 
date: 2022-12-04 06:35:07
hero_image: /img/am-powder.jpg
hero_height: is-large
hero_darken: true
image: /img/3dPrintedComponent.jpg
tags: 3DPrinting Sherbrooke Metal
---

The idea behind the 3d printer is to blablabalbabalbalaballablbala, frank was here

## GitHub Pages Configuration

GitHub pages allows you to create a website for your project with free hosting. Go to your repo on GitHub, then click Settings, then scroll down to the GitHub Pages section. You have the option to create a site from the root of your master branch of from the /docs directory in your master branch. For this example, we are going to use the /docs directory. 

Don't change this setting just yet as if you don't have a docs directory there will be nothing there to publish. 

## Creating the docs directory

Clone your git repo to a local directory, let's say `~/code/my-project` for this example. The below assumes you don't yet have a docs directory and you have [jekyll installed](https://jekyllrb.com/docs/installation/). If you do already have a docs directory you will have to rename it to something else. 

Create a new jekyll installation in the docs directory, ensuring you replace your username and project name in the below example.

```bash
git clone https://github.com/username/my-project.git ~/code/my-project
cd ~/code/my-project
jekyll new docs
```

You should now have a base install of Jekyll in your freshly created docs directory. 

## Configuring the theme

1. Replace everything in the Gemfile with the following
```
source 'https://rubygems.org'
gem "bulma-clean-theme",  '0.7.2'
gem 'github-pages', group: :jekyll_plugins
```

2. Open the `_config.yml` and comment out or delete the line `theme: minima` and replace it with `remote_theme: chrisrhymes/bulma-clean-theme`, then add `github-pages` to the list of plugins. Update the baseurl to your GitHub repo name, in this example we are using `my-project` as the repo name
```yaml
#theme: minima
remote_theme: chrisrhymes/bulma-clean-theme
baseurl: "/my-project"
plugins:
- github-pages
```

3. Open the `index.md` file and update the front matter so the layout is page and then add a title
```yaml
layout: page
title: Docs for My Project
```

4. Run `bundle install` and then `bundle exec jekyll serve`

5. Visit `http://localhost:4000/my-project/` to view your new docs page.

