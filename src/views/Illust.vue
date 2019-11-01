<template>
  <div>
    <loading v-if="!has_data" />
    <div class="container grid-lg" style="padding-top:2em;padding-bottom:10em" v-if="has_data">
      <div class="columns">
        <div class="column col-1"></div>
        <div class="column col-10">
          <div class="tile">
            <div class="tile-icon">
              <figure class="avatar avatar-lg">
                <a :href="'https://www.pixiv.net/member.php?id=' + data.author.id">
                  <img :src="data.author.avatar" alt="..." />
                </a>
              </figure>
            </div>
            <div class="tile-content">
              <p class="tile-title">
                <span class="text-bold text-large lang-ja" lang="ja">{{ data.title }}</span>
                <br />
                <span class="text-gray lang-ja" lang="ja">
                  by
                  <a
                    :href="'https://www.pixiv.net/member.php?id=' + data.author.id"
                    lang="ja"
                  >{{ data.author.name }}</a>
                </span>&nbsp;&nbsp;
                <span
                  class="text-gray lang-ja"
                  id="created_by"
                  lang="ja"
                >{{ data.created_at }}</span>
              </p>
              <p class="tile-subtitle lang-ja" lang="ja" v-html="data.description"></p>
              <div class="tile-action">
                <span
                  class="label label-rounded lang-ja"
                  lang="ja"
                  style="margin: 0.2em 0.1em"
                  v-for="tag in data.tags"
                  :key="tag"
                >{{ tag }}</span>
              </div>
            </div>
          </div>
        </div>
        <div class="column col-1"></div>
      </div>
      <div class="columns" style="padding-top:1em">
        <div class="column col-1"></div>
        <div class="column col-10">
          <img
            v-for="url in data.sources"
            :key="url"
            :src="url"
            class="img-responsive"
            style="padding-top:1em"
          />
        </div>
        <div class="column col-1"></div>
      </div>
    </div>
  </div>
</template>

<script>
import Loading from '@/components/Loading.vue';

export default {
  name: 'Illust',
  components: {
    Loading,
  },
  data() {
    return {
      data: {},
      has_data: false,
    };
  },
  created() {
    this.fetchData();
  },
  watch: {
    // call again the method if the route changes
    $route: 'fetchData',
  },
  methods: {
    fetchData() {
      fetch(`//localhost:9090/${this.$route.params.pixiv_id}.json`, {
        method: 'GET', // *GET, POST, PUT, DELETE, etc.
        mode: 'cors', // no-cors, *cors, same-origin
        headers: {
          Accept: 'application/json',
          'Content-Type': 'application/json',
        },
      }).then((resp) => {
        resp
          .json()
          .then((data) => {
            this.data = data;
            this.data.created_at = this.formatDate(data.created_at);
            this.has_data = true;
          })
          .catch(() => {
            this.$router.replace('/404');
          });
      });
    },
    formatDate: (t) => {
      const nt = new Date(t * 1000);
      const options = {
        weekday: 'short',
        year: 'numeric',
        month: 'long',
        day: 'numeric',
        hour: 'numeric',
        minute: 'numeric',
        second: 'numeric',
      };
      return nt.toLocaleDateString('ja-JP', options);
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
