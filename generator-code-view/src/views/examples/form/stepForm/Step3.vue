<template>
  <div>
    <a-form style="margin: 40px auto 0;">
    </a-form>
  </div>
</template>

<script>

  export default {
    name: "Step3",
    components: {
    },
    data () {
      return {
        loading: false
      }
    },
    methods: {
      finish () {
        this.$emit('finish')
      },
      toOrderList () {
        this.$router.push('/list/query-list')
      }
    }
  }
</script>
<style lang="less" scoped>
  .information {
    line-height: 22px;

    .ant-row:not(:last-child) {
      margin-bottom: 24px;
    }
  }
  .money {
    font-family: "Helvetica Neue",sans-serif;
    font-weight: 500;
    font-size: 20px;
    line-height: 14px;
  }
</style>