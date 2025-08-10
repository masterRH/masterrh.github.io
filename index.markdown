---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
title: "My learning notes"
---

## 最新文章

{% for post in site.posts limit:10 %}
<div class="post-preview">
  <h3><a href="{{ post.url | relative_url }}">{{ post.title }}</a></h3>
  <p class="post-meta">
    <time datetime="{{ post.date | date_to_xmlschema }}">
      {{ post.date | date: "%Y年%m月%d日" }}
    </time>
    {% if post.categories %}
      • 分类: {{ post.categories | join: ", " }}
    {% endif %}
  </p>
  {% if post.excerpt %}
    <p class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 50 }}</p>
  {% endif %}
</div>
<hr>
{% endfor %}

## 所有文章

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url | relative_url }}) - {{ post.date | date: "%Y年%m月%d日" }}
{% endfor %}
