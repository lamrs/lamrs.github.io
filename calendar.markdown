---
layout: page
title: Calendar
permalink: /calendar/
---

{%- if site.posts.size > 0 -%}
  The club will post updates on the progress of the new layout in this space. Tune in often to see what’s going on.
  <br><br>
  <ul class="post-list">
    {%- for post in site.posts -%}
    <li>
      {%- assign date_format = site.minima.date_format | default: "%B %-d, %Y" -%}
      <!-- <span class="post-meta">{{ post.date | date: date_format }}</span> -->
      <h3>
        <a class="post-link red" href="{{ post.url | relative_url }}">
          {{ post.date | date: date_format | post.title | escape }}
        </a>
        <strong>{{ post.title }}</strong>
      </h3>
      {%- if site.show_excerpts -%}
        {{ post.excerpt }}
        {% if post.content.size > post.excerpt.size %}
          <p><a href="{{ post.url }}">(more...)</a></p>
        {%- endif -%}
      {%- else -%}
        {{ post.content }}
      {%- endif -%}
    </li>
    {%- endfor -%}
  </ul>
  <p class="rss-subscribe">subscribe <a href="{{ "/feed.xml" | relative_url }}">via RSS</a></p>
{%- endif -%}
