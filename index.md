---
layout: default
title: Home
---

<div id="app">
  <home-page></home-page>
</div>

<script src="https://cdn.jsdelivr.net/npm/vue@2"></script>
<script>
  Vue.component('home-page', {
    template: `
      <div class="home-content">
        <h1>Welcome to xBei's Blog</h1>
        <p>一个脑子不灵光的人.</p>
        <div class="personal-info">
          <a href="https://space.bilibili.com/367457335" target="_blank">
            <i class="fab fa-bilibili"></i> Bilibili
          </a>
          <a href="https://github.com/xBei0223" target="_blank">
            <i class="fab fa-github"></i> GitHub
          </a>
        </div>
        <div class="blog-content">
          <ul>
            {% assign count = 0 %}
            {% for post in site.posts %}
              {% if count < 5 %}
                <li class="post-item">
                  <a href="{{ post.url | relative_url }}"><h2>{{ post.title }}</h2></a>
                  <p class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 50 }}</p>
                  <a href="{{ post.url | relative_url }}">Read more...</a>
                  <span class="post-date">{{ post.date | date: '%B %d, %Y' }}</span>
                </li>
                {% assign count = count | plus: 1 %}
              {% endif %}
            {% endfor %}
          </ul>
        </div>
      </div>
    `
  });

  new Vue({
    el: '#app'
  });
</script>
