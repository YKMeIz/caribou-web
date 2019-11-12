<template>
  <div class="container grid-lg">
    <div class="columns">
      <div class="column col-1"></div>
      <div class="column col-10">
        <h2 class="text-center">使用幫助</h2>
        <br />
        <p class="lang-zh-hans">
          這個網站提供直接訪問
          <a href="https://www.pixiv.net">Pixiv</a>
          (P站)圖片及相關信息的服務。除圖片外、還可獲得包含作者頭像、作者名、作品名、作品發布時間、作品描述、作品標籤等額外信息。
          使用方式如下：
        </p>
        <br />
        <h4>通過圖片ID訪問相關信息</h4>
        <pre class="code"><code># 網站域名+P站圖片ID
<a href="https://pximg.ykz.dev/73869218">https://pximg.ykz.dev/73869218</a></code></pre>
        <br />
        <h4>通過文件名直接訪問圖片文件</h4>
        <pre class="code"><code># 網站域名+P站圖片文件名
<a href="https://pximg.ykz.dev/73869218_p0.png">https://pximg.ykz.dev/73869218_p0.png</a>

# P站圖片文件網址替換 (i.pximg.net -> pximg.ykz.dev)
# 作品圖片
<a
  href="https://pximg.ykz.dev/img-original/img/2019/03/25/19/00/00/73869218_p0.png"
>https://pximg.ykz.dev/img-original/img/2019/03/25/19/00/00/73869218_p0.png</a>
# 作者頭像
<a
  href="https://pximg.ykz.dev/user-profile/img/2012/02/20/20/39/04/4236630_43ff9b8f7e2b4182c8ecb85974e4364f_50.gif"
>https://pximg.ykz.dev/user-profile/img/2012/02/20/20/39/04/4236630_43ff9b8f7e2b4182c8ecb85974e4364f_50.gif</a></code></pre>
        <br />
        <h4>通過圖片ID調用API接口</h4>
        <pre class="code"><code># 網站域名+P站圖片ID.json
<a href="https://pximg.ykz.dev/73869218.json">https://pximg.ykz.dev/73869218.json</a></code></pre>
        <p class="lang-zh-hans">另一種方式是在HTTP請求頭文件里包含 Accept 參數：</p>
        <pre class="code" data-lang="bash"><code>curl --header "Accept: application/json" https://pximg.ykz.dev/73869218</code></pre>
        <p class="lang-zh-hans">兩者返回的內容是一樣的：</p>
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
