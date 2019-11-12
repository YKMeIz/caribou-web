<template>
  <div>
    <div class="input-group">
      <span class="input-group-addon hide-xs">pximg.ykz.dev/</span>
      <input type="text" v-model="id" class="form-input lang-ja"
             placeholder="Pixiv作品ID。例：73869218" @keydown.enter="view" />
      <button @click="view" class="btn btn-primary input-group-btn lang-zh-hans">查看</button>
    </div>
    <ul class="nav">
      <li class="nav-item">
        <router-link class="lang-ja" lang="ja" to="/help">使用幫助</router-link>
      </li>
      <li class="nav-item">
        <router-link class="lang-ja" lang="ja" to="/about">其它說明</router-link>
      </li>
      <li class="nav-item">
        <a class="lang-ja" href="//github.com/YKMeIz/caribou" lang="ja">GitHub</a>
      </li>
    </ul>
  </div>
</template>

<script>
export default {
  name: 'Search',
  data() {
    return {
      id: '',
    };
  },
  methods: {
    view() {
      this.$router.push({ path: this.id });
    },
  },
};
</script>

<style scoped>
.input-group {
  max-width: 23rem;
  margin: auto;
  padding-bottom: 2rem;
}
</style>
