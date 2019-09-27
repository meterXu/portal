<template>
  <div class="project-list">

    <a
      :href="post.frontmatter.url"
      v-for="post in posts"
      :key="post.title"
      class="post"
      :style="{ backgroundImage: `url(${post.frontmatter.thumbnail})` }"
    >

      <div class="info">
        <h2>{{ post.frontmatter.title }}</h2>
        <span v-if="post.frontmatter.description">{{ post.frontmatter.description }}</span>
      </div>

    </a>

  </div>
</template>

<script>
  export default {
    computed: {
      posts() {
        return this.$site.pages
          .filter(x => x.path.startsWith('/works/') && !x.frontmatter.works_index)
          .sort((a, b) => a.frontmatter.sort - b.frontmatter.sort)
      }
    }
  }
</script>

<style scoped>

  .post {
    display: block;
    position: relative;
    width: 100%;
    height: 70vh;
    background-size: cover;
    background-position: center;
    background-repeat: no-repeat;
    margin-bottom: 5vw;
    cursor: pointer;
  }

  .info {
    position: absolute;
    left: 0;
    top: 2rem;
    padding: 0.5rem 1rem;
    background: rgba(255,255,255, 1);
    max-width: 400px;
    color: #1c1c1c;
  }

  .info h2 {
    display: inline-block;
    width: auto;
    font-size: 0.8rem;
    font-weight: 700;
    margin: 0;
  }

  .info span {
    display: inline-block;
    width: auto;
    margin: 0;
    margin-left: 0.5rem;
    font-size: 0.8rem;
  }

</style>
