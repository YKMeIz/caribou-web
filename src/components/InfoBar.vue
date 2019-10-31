<template>
  <div class="hero hero-sm bg-primary">
    <div class="container">
    <header class="navbar">
      <section class="navbar-section">
        <router-link class="text-light lang-ja" lang="ja" to="/">
          &copy; 2019 カリブープロジェクト
        </router-link>
      </section>
      <section class="navbar-section">
        <router-link class="text-light lang-ja" lang="ja" to="/help">使用幫助</router-link>
        <router-link class="text-light lang-ja" lang="ja" to="/about">其它說明</router-link>
        <a class="text-light lang-ja" lang="ja" href="//github.com/YKMeIz/caribou">GitHub</a>
      </section>
    </header>
    </div>
  </div>
</template>

<script>
export default {
  name: 'InfoBar',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.text-light {
  padding: 0 0.4rem;
}
.hero {
  height: 12vh;
}
</style>
