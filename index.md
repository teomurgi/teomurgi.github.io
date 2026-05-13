---
layout: default
---

<h1>{{ site.title }}</h1>
<p class="tagline">{{ site.description }}</p>

<section class="posts">
  {% for post in site.posts %}
  <article class="post">
    <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%Y-%m-%d" }}</time>
    <h2><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h2>
    {% if post.tags %}
    <div class="tags">
      {% for tag in post.tags %}
      <span class="tag">{{ tag }}</span>
      {% endfor %}
    </div>
    {% endif %}
    <div class="excerpt">{{ post.excerpt | markdownify | strip_html | truncate: 150 }}</div>
  </article>
  {% endfor %}
</section>
