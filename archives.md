---
layout: page
title: All yearbook are here
titlebar: archives
subtitle: <span class="mega-octicon octicon-calendar"></span>&nbsp;&nbsp;年鉴系列
menu: archives
css: ['blog-page.css']
permalink: /archives.html
---

<ul class="archives-list">
            <h3>2010-2018</h3>
            {% for item in site.data.pdf_address %}
            <li >  <a  href="{{ item.address }}">{{ item.name }}</a> </li>
            {% endfor %}
</ul>

<ul class="archives-list">
  {% for post in site.posts %}
    {% unless post.next %}
      <h3>{{ post.date | date: '%Y' }}</h3>
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <h3>{{ post.date | date: '%Y' }}</h3>
      {% endif %}
    {% endunless %}
    <li><span>{{ post.date | date:'%m-%d' }}</span> <a href="{{ site.url }}{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
