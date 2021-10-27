---
title: "Welcome to my blog"
# layout: default
---

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

I'm glad you are here. I plan to talk about a lot of stuff. I think.

<br>

{% include 01-links.md %}