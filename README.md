# KosmoKot

A responsive, dark and simple [Hexo](https://hexo.io) theme for a personal website based on [Cactus-dark theme 2.0](https://github.com/probberechts/hexo-theme-cactus)

## Summary

- [General](#general)
- [Features](#features)
- [Install](#install)
- [Configuration](#configuration)
- [Layouts](#Layouts)
- [License](#license)

## General

- **Version** : 1.0 *(Based on Cactus dark 2.0)*
- **Compatibility** : Hexo 3+

## Features

- Fully responsive
- Disqus
- Googe analytics
- Font Awesome icons
- Pick your own code highlighting scheme
- Configurable navigation menu
- Support for local search
- Github issues as comments
- Additional layouts (Download/Tag cloud)
- Simplicity

## Install
1. In the `root` directory:

    ```git
    $ git clone https://github.com/Tym17/KosmoKot.git themes/KosmoKot
    $ npm install hexo-pagination --save
    $ npm install hexo-reading-time --save
    ```

2. Change the `theme` property in the `config.yml` file.

    ```yml
    # theme: landscape
    theme: KosmoKot
    ```

4. [Configuration](#configuration)

3. Run: `hexo generate` and `hexo server`

## Configuration

### Navigation

Setup the navigation menu in the theme's `_config.yml`:

  ```yml
# ...
  nav:
    Home: /
    About: /about/
    Writing: /archives/
    Projects: http://github.com/probberechts
    LINK_NAME: URL
# ...
  ```

### Blog posts list on home page

You have two options for the list of blog posts on the home page:

  - Show only the 5 most recent posts (default)

  ```yml
# ...
  customize:
    show_all_posts: false
    post_count: 5
# ...
  ```

  - Show all posts 

  ```yml
# ...
  customize:
    show_all_posts: true
# ...
  ```

### Projects list

Create a projects file `source/_data/projects.json`.

  ```json
  [
      {
         "name":"Hexo",
         "url":"https://hexo.io/",
         "desc":"A fast, simple & powerful blog framework"
      },
      {
         "name":"Font Awesome",
         "url":"http://fontawesome.io/",
         "desc":"The iconic font and CSS toolkit"
      }
  ]
  ```

### Social media links

Cactus Dark can automatically add links to your social media accounts. Therefore, update the theme's `_config.yml`:

  ```yml
# ...
  customize:
    social_links:
      github: your-github-url
      twitter: your-twitter-url
      NAME: your-NAME-url
# ...
  ```

where `NAME` is the name of a [Font Awesome icon](http://fontawesome.io/icons/#brand).

### RSS

Set the `rss` field in the theme's `_config.yml` to the url you defined in the configuration of the [hexo-generator-feed](https://github.com/hexojs/hexo-generator-feed) plugin. or leave it empty.

### Analytics

Add you Google Analytics `tracking_id` to the theme's `_config.yml`.

  ```yml
# ...
  plugins:
      gooogle_analytics: 'UA-49627206-1'            # Format: UA-xxxxxx-xx
# ...
  ```

### Disqus Comments

First, create a site on Disqus: [https://disqus.com/admin/create/](http://disqus.com/admin/create/).

Next, update the theme's `_config.yml` file:

  ```yml
# ...
  plugins:
      disqus_shortname: SITENAME
# ...
  ```

where `SITENAME` is the name you gave your site on Disqus.

### Github issues as comments

1. Change the theme's `__config.yml` file according to your needs:

    ```yml
    # ...
    plugins:
        # Github Issues -> comments
        github_comments: Tym17/KosmoKot # Github repo for mirroring Issues to comments
        github_admins:
        - Tym17 # add your Github name or more if you want admin highlight on comments
    # ...
    ```

2. Pick which issue to mirror on which post. Add `gh_issue: 7` to load comments from issue #7 on the post like so at the beginning of a Markdown post in the Front Matter section:

    ```yml
    ---
    title: Making my own blog
    date: 2018-07-01 14:07:18
    author: You
    gh_issue: 7
    tags:
    - CSS
    - HTML
    ---
    # Markdown post content
    ```

3. Additionally add `gh_mods` to the Front Matter to have moderator highlight on comments:

    ```yml
    ---
    title: Making my own blog
    date: 2018-07-01 14:07:18
    author: You
    gh_issue: 7
    gh_mods:
    - Buddy17
    - Friend2
    tags:
    - CSS
    - HTML
    ---
    # Markdown post content
    ```

### Code Highlighting

Pick one of [the available colorschemes](https://github.com/probberechts/cactus-dark/tree/master/source/css/_highlight) and add it to the theme's `_config.yml`:

  ```yml
# ...
  customize:
      highlight: COLORSCHEME_NAME
# ...
  ```

### Local search

First, install the [hexo-generate-search](https://www.npmjs.com/package/hexo-generator-search) plugin, which will generate a search index file.

  ```git
  $ npm install hexo-generator-search --save
  ```

Next, create a page to display the search engine:

  ```sh 
  $ hexo new page Search
  ```
and put `search: true` in the front-matter.

Finally, edit the theme's `_config.yml` and add a link to the navigation menu.

  ```yml
# ...
  nav:
    # ...
    Search: /Search/
    # ...
# ...
  ```

### Change the colors

Edit `source/css/_variables.styl` to your liking:

```styl
// ...

// Colors
$color-background = #1d1f21
$color-date = #666
$color-text = #c9cacc
$color-light = #cccccc
$color-lightest = #eeeeee
$color-accent = #AE54FE
$color-link = desaturate($color-accent, 55%) // vimeo: :selection with alpha=1
$color-shadowbackground = mix(tint($color-background, 30), $color-accent, 60)

// ...
```

## Layouts

### Tag cloud

Add a `layout: tags` line in your Front Matter when writing a Markdown page like so:

```yml
---
title: Tag clouds 
layout: tags
---
Here you can see all the tags I used!
```

The content will be shown before the tag cloud is shown.

### Download page

1. Add a `layout: download` line in your Front Matter when writing a Markdown page like so:

    ```yml
    ---
    title: MySoft
    layout: download
    ---
    This is a super description of the software I made that is avaible for download!
    ```

2. Add a non-numbered list in the Markdown:

    ```yml
    ---
    title: MySoft
    layout: download
    ---
    This is a super description of the software I made that is avaible for download!
    
    * [Windows Version](https://your/soft/windows)
    * [Linux Version](https://your/soft/Linux)
    * [OSX Version](https://your/soft/OSX)
    ```

    It will automatically render as a list in the middle of the page with colored download icons next to them.


## License
MIT