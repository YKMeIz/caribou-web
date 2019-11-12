<template>
  <div class="empty">
    <div class="middle">
      <p class="empty-title h5 lang-zh-hans">快速訪問Pixiv作品信息</p>
      <div class="empty-action">
        <search />
      </div>
    </div>
  </div>
</template>

<script>
import Search from '@/components/Search.vue';

export default {
  name: 'Home',
  components: { Search },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.middle {
  padding-top: 20vh;
}
</style>
