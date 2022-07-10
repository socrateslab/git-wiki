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
- Second，I add a folder with the name "blog" and add an index.html file within it. 


```html
---
title: Wiki Pages
layout: git-wiki-default
---

<!-- This loops through the paginated posts -->
{% for post in paginator.posts %}
    <div class="post-item">
        <p class="author">
            <span class="date">{{ post.date | date: "%-d %B %Y"}}</span>
        </p>
        <div class="git-wiki-content">
            {{ post.excerpt }}

            <a href="{{ post.url | relative_url }}">...Read all</a>
        </div>
    </div>
    <hr>
{% endfor %}

<!-- Pagination links -->
<div class="pagination">
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path | relative_url }}" class="previous">
      Previous
    </a>
  {% else %}
    <span class="previous">Previous</span>
  {% endif %}
  <span class="page_number ">
    Page: {{ paginator.page }} of {{ paginator.total_pages }}
  </span>
  {% if paginator.next_page %}
    <a href="{{ paginator.next_page_path | relative_url }}" class="next">Next</a>
  {% else %}
    <span class="next ">Next</span>
  {% endif %}
</div>
```
