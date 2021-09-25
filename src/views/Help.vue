<template>
  <div class="container grid-lg">
    <div class="columns">
      <div class="column col-1"></div>
      <div class="column col-10">
        <h2 class="text-center">使用帮助</h2>
        <br />
        <p class="lang-zh-hans">
          这个网站提供直接访问
          <a href="https://www.pixiv.net">Pixiv</a>
          (P站)图片及相关信息的服务。除图片外、还可获得包含作者头像、作者名、作品名、作品发布时间、作品描述、作品标签等额外信息。
          使用方式如下：
        </p>
        <br />
        <h4>通过图片ID访问相关信息</h4>
        <pre class="code"><code># 网站域名+P站图片ID
<a href="https://caribou.ykmeiz.dev/73869218">https://caribou.ykmeiz.dev/73869218</a></code></pre>
        <br />
        <h4>通过文件名直接访问图片文件</h4>
        <pre class="code"><code># 网站域名+P站图片文件名
<a href="https://caribou.ykmeiz.dev/73869218_p0.png">https://caribou.ykmeiz.dev/73869218_p0.png</a>

# P站图片文件网址替换 (i.pximg.net -> caribou.ykmeiz.dev)
# 作品图片
<a
  href="https://caribou.ykmeiz.dev/img-original/img/2019/03/25/19/00/00/73869218_p0.png"
>https://caribou.ykmeiz.dev/img-original/img/2019/03/25/19/00/00/73869218_p0.png</a>
# 作者头像
<a
  href="https://caribou.ykmeiz.dev/user-profile/img/2012/02/20/20/39/04/4236630_43ff9b8f7e2b4182c8ecb85974e4364f_50.gif"
>https://caribou.ykmeiz.dev/user-profile/img/2012/02/20/20/39/04/4236630_43ff9b8f7e2b4182c8ecb85974e4364f_50.gif</a></code></pre>
        <br />
        <h4>通过图片ID调用API接口</h4>
        <pre class="code"><code># 网站域名+P站图片ID.json
<a href="https://caribou.ykmeiz.dev/73869218.json">https://caribou.ykmeiz.dev/73869218.json</a></code></pre>
        <p class="lang-zh-hans">另一种方式是在HTTP请求头文件里包含 Accept 参数：</p>
        <pre class="code" data-lang="bash"><code>curl --header "Accept: application/json" https://caribou.ykmeiz.dev/73869218</code></pre>
        <p class="lang-zh-hans">两者返回的内容是一样的：</p>
        <pre class="code" data-lang="json"><code>{
   "title":"嫌パン小説 第4-4話「よみがえり」",
   "id":"73869218",
   "description":"小説本文はこちら→https://ncode.syosetu.com/n5826ff/19/",
   "tags":[
      "オリジナル",
      "女の子",
      "嫌パン",
      "嫌な顔されながらおパンツ見せてもらいたいシリーズ",
      "メイド",
      "小説家になろう",
      "伊東ちとせ",
      "対物ライフル"
   ],
   "created_at":1553508000,
   "sources":[
      "https://i.pximg.net/img-original/img/2019/03/25/19/00/00/73869218_p0.png"
   ],
   "author":{
      "id":"554102",
      "name":"40原",
      "avatar":"https://i.pximg.net/user-profile/img/2012/02/20/20/39/04/4236630_43ff9b8f7e2b4182c8ecb85974e4364f_50.gif"
   }
}</code></pre>
      </div>
      <div class="column col-1"></div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'Help',
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.container {
  padding-top: 2rem;
  min-height: 88vh;
  padding-bottom: 5rem;
}
.text-center {
  margin-top: 3rem;
}
</style>
