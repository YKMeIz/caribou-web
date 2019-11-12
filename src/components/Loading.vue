<template>
  <div class="container load">
    <div class="loading loading-lg"></div>
    <p class="text-center lang-zh-hans">(っ・Д・)っ 努力加載中...</p>
  </div>
</template>

<script>
export default {
  name: 'Loading',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.load {
  height: 100vh !important;
  padding-top: 35vh !important;
}
.text-center {
    padding-top: 1rem;
}
</style>
