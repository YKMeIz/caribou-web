<template>
  <div class="empty">
    <div class="middle">
      <p class="empty-title h5">出錯啦：Σ(*ﾟдﾟﾉ)ﾉ</p><br>
      <p class="empty-subtitle">您所查詢的作品不存在；也有可能是其他未知原因。</p>
      <p class="empty-subtitle">總之、返回主頁重新搜索一遍吧。</p>
      <div class="empty-action">
          <button @click="$router.replace('/')" class="btn btn-primary lang-ja">返回主頁</button>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'NotFound',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.middle {
  padding-top: 23vh;
}
</style>
