---
layout: default
title: 개발 노트
description: papig이 만든 iPhone 앱들의 소개와 사용법을 정리한 개발 노트입니다.
permalink: /blog/
---

# 개발 노트

앱을 만들면서, 왜 만들었고 어떻게 쓰는지 남긴 글입니다.

<ul class="post-list">
{% for post in site.posts %}
  <li style="margin-bottom:1.4em">
    <a href="{{ post.url | relative_url }}" style="font-size:1.15em;font-weight:600">{{ post.title }}</a>
    <small style="opacity:0.6"> · {{ post.date | date: "%Y.%m.%d" }}</small>
    {% if post.description %}<div style="opacity:0.8;margin-top:2px">{{ post.description }}</div>{% endif %}
  </li>
{% endfor %}
</ul>
