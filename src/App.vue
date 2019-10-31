<template>
  <div id="app">
    <transition name="fade">
      <router-view />
    </transition>
    <info-bar />
  </div>
</template>

<script>
import InfoBar from '@/components/InfoBar.vue';

export default {
  name: 'App',
  components: {
    InfoBar,
  },
};
</script>

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
}
.fade-enter-active, .fade-leave-active {
  transition: opacity .5s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
