<template>
  <div class="container grid-lg">
    <div class="columns">
      <div class="column col-1"></div>
      <div class="column col-10">
        <h2 class="text-center">著作權聲明</h2>
        <p class="lang-zh-hans">
          這個網站只搬運圖片。
          <br />網站上所顯示的所有圖片作品、著作權均屬於作品作者。
          <br />可以通過作者名字或頭像、來訪問其P站個人頁面。
        </p>
        <br /><br />
        <h2 class="text-center">關於緩存數據</h2>
        <p class="lang-zh-hans">
          有時候訪問這個網站會有點兒慢、是因為作品元數據(即API請求結果里的內容)均從P站採集。
          <br />圖片文件以代理的方式從P站直接獲取、中間不經過壓縮或修改。
          <br />網站服務器只緩存作品元數據、緩存失效期限為24個小時。網站服務器不會緩存任何圖片文件。
          <br />
        </p>
        <br />
      </div>
      <div class="column col-1"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'About',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  padding-top: 2rem;
  min-height: 88vh;
}
.text-center {
  margin-top: 3rem;
}
</style>
