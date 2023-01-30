<template>
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
</template>

<script>
  export default {
    name: "LayoutFooter",
    data(){
      return {
        wechatImgUrl: require('@/assets/wechat/wechat.jpg')
      }
    }
  }
</script>

<style lang="less" scoped>
  .footer {
    padding: 0 16px;
    margin: 48px 0 24px;
    text-align: center;

    .links {
      margin-bottom: 8px;
      .footer-item {
        margin: 0 10px;
      }
      .footer-icon {
        margin-right: 5px;
      }
      a {
        color: rgba(0, 0, 0, .45);

        &:hover {
          color: rgba(0, 0, 0, .65);
        }

        &:not(:last-child) {
          margin-right: 40px;
        }
      }
    }
    .copyright {
      color: rgba(0, 0, 0, .45);
      font-size: 14px;
    }
  }
  .weichat {
    width: 150px;
    height: 150px;
  }
</style>