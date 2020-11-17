---
layout: page
title: Billets
permalink: /billets/
---
[Niouzletter du 09 novembre 2020]({{ '2020/11/09/Niouzletter-du-9-novembre.html' | relative_url}})

{% if site.paginate %}
    {% assign posts = paginator.posts %}
  {% else %}
    {% assign posts = site.posts %}
  {% endif %}
  

{%- if posts.size > 0 -%}
<h2>Billets</h2>
<ul class="post-list">
    {%- assign date_format = site.minima.date_format | default: "%-d %b, %Y" -%}
    {%- for post in posts -%}
    {%- if posts.published != "false" -%}
    <li>
    <span class="post-meta">{{ post.date | date: date_format }}</span>
    <h3>
        <a class="post-link" href="{{ post.url | relative_url }}">
        {{ post.title | escape }}
        </a>
    </h3>
    {%- if site.show_excerpts -%}
        {{ post.excerpt }}
    {%- endif -%}
    </li>
    {%- endif -%}
    {%- endfor -%}
</ul>

{% if site.paginate %}
    <div class="pager">
    <ul class="pagination">
    {%- if paginator.previous_page %}
        <li><a href="{{ paginator.previous_page_path | relative_url }}" class="previous-page">{{ paginator.previous_page }}</a></li>
    {%- else %}
        <li><div class="pager-edge">•</div></li>
    {%- endif %}
        <li><div class="current-page">{{ paginator.page }}</div></li>
    {%- if paginator.next_page %}
        <li><a href="{{ paginator.next_page_path | relative_url }}" class="next-page">{{ paginator.next_page }}</a></li>
    {%- else %}
        <li><div class="pager-edge">•</div></li>
    {%- endif %}
    </ul>
    </div>
{%- endif %}

  {%- endif -%}
