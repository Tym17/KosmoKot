---
title: Hello Github
date: 2018-09-10 15:20:57
gh_issue: 1
tags:
- Github
- CSS
- Javascript
- Ajax
---

## Github issues as comments

### How to

1. Change the theme's `__config.yml` file according to your needs:

    ```yml
    # ...
    plugins:
        # Github Issues -> comments
        github_comments: Tym17/KosmoKot # Github repo
        github_admins:
        - Tym17 # add your Github name or more
    # ...
    ```

2. Pick which issue to mirror on which post. Add `gh_issue: 1` to load comments from issue #1 on the post like so at the beginning of a Markdown post in the Front Matter section:

    ```yml
    ---
    title: Hello Github
    date: 2018-09-10 15:20:57
    gh_issue: 1
    tags:
    - Github
    - CSS
    - Javascript
    - Ajax
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


### Effects

Github users who have their username in one of those list will have a different color on the left of their comments so reader can identify them.

Admin(s) will have a border of the same color as the blog's accent while Moderator(s) will have a border colored with the post's text color.