<template>
  <footer id="footer">
    <div v-if="$route.path.indexOf('article') !== -1">
      <div class="g-bolang">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          viewBox="0 0 54 14"
          height="70"
          preserveAspectRatio="none"
        >
          <path
            class="g-bolang-svg"
            d="M 27 10C 21 12 14 14 0 14L 0 0L 54 0L 54 3C 40 3 33 8 27 10Z"
          ></path>
        </svg>
      </div>
      <div class="container g-r-center">
        <hot-article :hots="hots"/>
        <tags/>
      </div>
    </div>
    <div class="put-on-record g-c-center">
      <p>
        ©2017-至今&nbsp;&nbsp;朱为鹏&nbsp;&nbsp;
        <a
          href="http://www.miitbeian.gov.cn/"
          target="_blank"
        >浙ICP备17031040号-3</a>
      </p>
      <p>
        感谢
        <a href="https://www.qiniu.com/" target="_blank">七牛云存储</a> 提供图片存储空间
      </p>
      <p>
        服务器、域名购置于
        <a href="https://www.aliyun.com/" target="_blank">阿里云</a>&nbsp;&nbsp;&nbsp;&nbsp;icon图标来源于
        <a href="http://www.iconfont.cn/" target="_blank">阿里巴巴矢量图标库</a>
      </p>
    </div>
  </footer>
</template>

<script lang='ts'>
'use strict'
import { Vue, Component, Prop } from 'vue-property-decorator'
import hotArticle from '~/components/hotArticle.vue'
import tags from '~/components/tags.vue'

@Component({
  components: { hotArticle, tags }
})
export default class Footer extends Vue {
  @Prop(Array)
  readonly hots!: object[]
}
</script>

<style lang="scss" scoped>
#footer {
  position: relative;
  z-index: 100;
  width: 100%;
  margin-top: -1px;
  overflow: hidden;
  background: -webkit-linear-gradient(45deg, #1e212b, #373b4d);
  background: linear-gradient(45deg, #1e212b, #373b4d);
  &.article {
    position: static;
    height: auto;
  }
  &.fixed {
    position: fixed;
    bottom: 0;
  }
  .container {
    margin: 0 auto;
    padding: 100px 0 0 !important;
    align-items: flex-start;
  }
  .put-on-record {
    height: 100px;
    line-height: 22px;
    color: #cecec4;
    text-align: center;
    font-size: 10px;
    a {
      color: #fff;
    }
  }
}

@media (min-width: 900px) {
  .container {
    max-width: 740px !important;
  }
}

@media (max-width: 550px) {
  .container {
    display: block !important;
  }
}
</style>
