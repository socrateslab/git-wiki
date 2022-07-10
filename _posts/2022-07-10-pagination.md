---
published: true
---

# How to show all the posts or pages?

I am wondering how to show all the posts or pages. So I ask a question on **[Drassil/git-wiki-theme#96](https://github.com/Drassil/git-wiki-theme/issues/96)**


According to the reply of Drassil, to add a pagination could be a solution. 
- [https://jekyllrb.com/docs/pagination/](https://jekyllrb.com/docs/pagination/)

Note that, there are both pages and posts on this wiki. And pagination seems to only wokr for posts.

According to [https://github.com/Drassil/git-wiki/blob/gh-pages/_config.yml](https://github.com/Drassil/git-wiki/blob/gh-pages/_config.yml), I need to revise the config file as follows:

```jekyll
 -
    scope:
      path: assets/blog
    values:
      layout: "git-wiki-blog"
```

## Solution

- First, I fork the [https://github.com/Drassil/git-wiki/](https://github.com/Drassil/git-wiki/). 
- Second，I add a folder with the name "blog" and add an **index.html** file within it. 

The content of the index.html is given as follows: [https://github.com/socrateslab/wiki/blob/gh-pages/blog/index.html](https://github.com/socrateslab/wiki/blob/gh-pages/blog/index.html)


