<template>
  <div class="container">
    <div class="text-right" v-if="this.$route.path !== '/'">
      <button class="btn btn-link" @click="activeModal">
        <i class="icon icon-menu"></i>
      </button>
    </div>

    <div :class="modalClass" id="modal-id">
      <a @click="closeModal" class="modal-overlay" aria-label="Close"></a>
      <div class="modal-container">
        <div class="modal-header">
          <a @click="closeModal" class="btn btn-clear float-right" aria-label="Close"></a>
          <div class="modal-title h5 text-center">快速訪問Pixiv作品信息</div>
        </div>
        <div class="modal-body">
          <div class="content text-center">
            <search class="search" />
          </div>
        </div>
        <div class="modal-footer">
          <div class="text-right gray lang-ja" lang=ja>
            &copy; 2019 <router-link class="gray" to="/">カリブープロジェクト</router-link>
          </div>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Search from '@/components/Search.vue';

export default {
  name: 'InfoBar',
  components: { Search },
  data() {
    return {
      modalClass: 'modal',
    };
  },
  watch: {
    $route: 'closeModal',
  },
  methods: {
    activeModal() {
      const wd = window.innerWidth
        || document.documentElement.clientWidth
        || document.body.clientWidth;
      if (wd <= 480) {
        this.modalClass = 'modal modal-lg active';
        return;
      }
      this.modalClass = 'modal active';
    },
    closeModal() {
      this.modalClass = 'modal';
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  padding: 0.4rem;
  height: 5vh;
}
.search {
  margin: auto;
}
.modal-footer {
  margin-top: 2rem;
  color: #bcc3ce;
}
.gray {
  color: #66758c;
}
</style>
