---
layout: page
tagline: Supporting tagline
---
{% include JB/setup %}

<ul class="post">
  {% for post in site.posts %}
    <li>
    <span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a>
      {% if post.content contains '<!--more-->' %}
        {{ post.content | split: '<!--more-->' | first | strip_html | newline_to_br}}
      {% else %}
        {{ post.content | split: '</p>' | first | strip_html | newline_to_br}}
      {% endif %}
    </li>
  {% endfor %}
</ul>


<ul class="posts">
  {% for post in site.posts %}
    <li><span>{{ post.date | date_to_string }}</span> &raquo; <a href="{{ BASE_PATH }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>

