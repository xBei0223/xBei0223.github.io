---
layout: blog
title: Blog
permalink: /blog/
---

<div id="app">
  <blog-page></blog-page>
</div>

<script src="https://cdn.jsdelivr.net/npm/vue@2"></script>
<script>
  Vue.component('blog-page', {
    template: `
      <div class="home-content">
        <h1>{{ page.title }}</h1>
        <div class="blog-content">
          <ul>
            {% for post in site.posts %}
              <li class="post-item">
                <a href="{{ post.url | relative_url }}"><h2>{{ post.title }}</h2></a>
                <p class="post-excerpt">{{ post.excerpt | strip_html | truncatewords: 50 }}</p>
                <a href="{{ post.url | relative_url }}">Read more...</a>
                <span class="post-date">{{ post.date | date: '%B %d, %Y' }}</span>
              </li> 
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
