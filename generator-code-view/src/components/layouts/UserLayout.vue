<template>
  <div id="userLayout" :class="['user-layout-wrapper', device]">
    <div class="container">
      <div class="top">
        <div class="header">
          <a href="/">
            <img src="~@/assets/logo.svg" class="logo" alt="logo">
            <span class="title">低代码生成器</span>
          </a>
        </div>
        <div class="desc">
          用极简的方式，快速构建代码结构
        </div>
      </div>

      <route-view></route-view>

      <div class="footer">
        <div class="links">
          <a-tooltip class="footer-item" placement="top">
            <template slot="title">
              <span>欢迎提出建议和 Bug 反馈</span>
            </template>
            <a-icon class="footer-icon" type="bug" />
            <a href="https://github.com/pdxjie/low-code/issues" class="anthor">产品反馈</a>
          </a-tooltip>
          <a-tooltip class="footer-item" placement="top">
            <template slot="title">
          <span>
            <img :src="wechatImgUrl" class="weichat" alt="">
          </span>
            </template>
            <a-icon class="footer-icon" type="message" />
            <span class="anthor">联系作者</span>
          </a-tooltip>
          <a-tooltip class="footer-item" placement="top">
            <template slot="title">
              <span> 查看本站源码，欢迎 star 🌟</span>
            </template>
            <a-icon class="footer-icon" type="github" />
            <a href="https://github.com/pdxjie/low-code" class="anthor">支持项目</a>
          </a-tooltip>
        </div>
        <div class="copyright">
          Copyright
          <a-icon type="copyright"/>
          2022 Create By PDX
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  import RouteView from "@/components/layouts/RouteView"
  import { mixinDevice } from '@/utils/mixin.js'

  export default {
    name: "UserLayout",
    components: { RouteView },
    mixins: [mixinDevice],
    data () {
      return {
        wechatImgUrl: require('@/assets/wechat/wechat.jpg')
      }
    },
    mounted () {
      document.body.classList.add('userLayout')
    },
    beforeDestroy () {
      document.body.classList.remove('userLayout')
    },
  }
</script>

<style lang="less" scoped>
  #userLayout.user-layout-wrapper {
    height: 100%;

    &.mobile {
      .container {
        .main {
          max-width: 368px;
          width: 98%;
        }
      }
    }
    .container {
      width: 100%;
      min-height: 100%;
      background: #f0f2f5 url(~@/assets/background.svg) no-repeat 50%;
      background-size: 100%;
      padding: 110px 0 144px;
      position: relative;

      a {
        text-decoration: none;
      }

      .top {
        text-align: center;

        .header {
          height: 44px;
          line-height: 44px;

          .badge {
            position: absolute;
            display: inline-block;
            line-height: 1;
            vertical-align: middle;
            margin-left: -12px;
            margin-top: -10px;
            opacity: 0.8;
          }

          .logo {
            height: 44px;
            vertical-align: top;
            margin-right: 16px;
            border-style: none;
          }

          .title {
            font-size: 33px;
            color: rgba(0, 0, 0, .85);
            font-family: "Chinese Quote", -apple-system, BlinkMacSystemFont, "Segoe UI", "PingFang SC", "Hiragino Sans GB", "Microsoft YaHei", "Helvetica Neue", Helvetica, Arial, sans-serif, "Apple Color Emoji", "Segoe UI Emoji", "Segoe UI Symbol";
            font-weight: 600;
            position: relative;
            top: 2px;
          }
        }
        .desc {
          font-size: 14px;
          color: rgba(0, 0, 0, 0.45);
          margin-top: 12px;
          margin-bottom: 40px;
        }
      }

      .main {
        min-width: 260px;
        width: 368px;
        margin: 0 auto;
      }

      .footer {
        position: absolute;
        width: 100%;
        bottom: 0;
        padding: 0 16px;
        margin: 48px 0 24px;
        text-align: center;

        .links {
          margin-bottom: 8px;
          font-size: 14px;
          .footer-item {
            margin: 0 10px;
          }
          .footer-icon {
            margin-right: 5px;
          }
          a {
            color: rgba(0, 0, 0, 0.45);
            transition: all 0.3s;
            &:not(:last-child) {
              margin-right: 40px;
            }
          }
        }
        .copyright {
          color: rgba(0, 0, 0, 0.45);
          font-size: 14px;
        }
      }
    }
  }
  .weichat {
    width: 150px;
    height: 150px;
  }
</style>