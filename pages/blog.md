---
title: Blog
nav: Blog
nav_order: 4
---
  

{% assign posts = site.posts %}
 


{%- if posts.size > 0 -%}
  {%- if page.list_title -%}
    <h2 class="post-list-heading">{{ page.list_title }}</h2>
  {%- endif -%}
  <ul class="post-list">
    {%- assign date_format = site.minima.date_format | default: "%b %-d, %Y" -%}
    {%- for post in posts -%}
    <li>
      <div class="post-card">
        {% if post.image %}
        <img src="{{ '/assets/img/' | append: post.image | relative_url }}" class="blog-roll-image" alt="post.image-alt"> 
        {% endif %}
        <div class="post-card-content">
          <h2>
            <a class="post-link" href="{{ post.url | relative_url }}">
              {{ post.title | escape }}
            </a>
          </h2>
          {%- if site.show_excerpts -%}
            <p>{{ post.excerpt | markdownify }}</p>
          {%- endif -%}
          <span class="post-meta">{{ post.date | date: date_format }}</span>
        </div>
      </div>
    </li>
    {%- endfor -%}
  </ul>
{%- endif -%}
