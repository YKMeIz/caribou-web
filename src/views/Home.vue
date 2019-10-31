<template>
  <div class="empty">
    <div class="middle">
      <p class="empty-title h5 lang-zh-hans">快速訪問Pixiv作品信息</p>
      <div class="empty-action">
        <div class="input-group">
          <span class="input-group-addon">pximg.ykz.dev/</span>
          <input type="text" v-model="id" class="form-input lang-ja"
            placeholder="Pixiv作品ID。 例：73869218" @keydown.enter="view" />
          <button @click="view" class="btn btn-primary input-group-btn lang-zh-hans">查看</button>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Home',
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

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.empty {
  height: 100vh;
}
.middle {
  padding-top: 30vh;
}
.input-group {
  max-width: 30rem;
  margin: auto;
}
</style>
