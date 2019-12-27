<template>
  <div class="text">
    <span class="author">{{ $site.themeConfig.footer }}</span>
    <span>|</span>
    <a class="record" :href="$site.themeConfig.record.url" target="_blank">{{ $site.themeConfig.record.title }}</a>
  </div>
</template>

<style scoped>
  .text {
    display: block;
    font-size: 0.8rem;
    text-align: left;
    padding: 4rem 5vw;
  }
  .record{
    color: #1c1c1c;
    text-decoration: none;
  }
  .record:hover{
    color: #c53a31;
  }
</style>
