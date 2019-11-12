<template>
  <div id="app">
    <info-bar />
    <transition name="fade">
      <router-view />
    </transition>
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

.empty {
  height: 95vh !important;
  background: #fff !important;
}

@media (prefers-color-scheme: dark) {
  #app, .empty, body {
    color: #eeeeee !important;
    background-color: #1c1c1c !important;
  }

  .modal-overlay {
    background: RGBA(28, 28, 28, 0.75) !important;
  }

  .modal.modal-lg .modal-overlay {
    background: #161616 !important;
  }

  code,
  input,
  .input-group-addon,
  .label,
  .hero,
  .modal-container,
  .modal-title,
  .modal-body,
  .modal-footer {
    color: #aaaaaa !important;
    background-color: #161616 !important;
  }

  .btn-primary {
    border-color: #bcc3ce !important;
    color: #eeeeee !important;
  }
  .input-group-addon {
    background: #282828 !important;
  }
}
</style>
