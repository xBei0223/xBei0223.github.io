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
      </div>
    `
  });

  new Vue({
    el: '#app'
  });
</script>
