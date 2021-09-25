<template>
  <div class="container grid-lg">
    <div class="columns">
      <div class="column col-1"></div>
      <div class="column col-10">
        <h2 class="text-center">著作权声明</h2>
        <p class="lang-zh-hans">
          这个网站只搬运图片。
          <br />网站上所显示的所有图片作品、著作权均属于作品作者。
          <br />可以通过作者名字或头像、来访问其P站个人页面。
        </p>
        <br /><br />
        <h2 class="text-center">关于缓存数据</h2>
        <p class="lang-zh-hans">
          有时候访问这个网站会有点儿慢、是因为作品元数据(即API请求结果里的内容)均从P站采集。
          <br />图片文件以代理的方式从P站直接获取、中间不经过压缩或修改。
          <br />网站服务器只缓存作品元数据、缓存失效期限为24个小时。网站服务器不会缓存任何图片文件。
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
