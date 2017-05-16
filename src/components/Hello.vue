<template>
  <div>
    <mt-header fixed title="标题">
      <router-link to="/" slot="left">
        <mt-button icon="back">返回</mt-button>
      </router-link>
    </mt-header>

    <div class="page-toast-wrapper">
      <mt-button @click.native="openToast" size="large">点击弹出 Toast</mt-button>
      <mt-button @click.native="openToastWithIcon" size="large">点击弹出带有 icon 的 Toast</mt-button>
      <mt-button @click.native="openBottomToast" size="large">自定义 Toast 位置</mt-button>
    </div>
  </div>
</template>

<script>
  import { Toast } from 'mint-ui'

  export default {
    methods: {
      openToast () {
        Toast('提示信息')
      },
      openToastWithIcon () {
        Toast({
          message: '操作成功',
          iconClass: 'mintui mintui-success'
        })
      },
      openBottomToast () {
        Toast({
          message: '提示信息',
          position: 'bottom'
        })
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="less">
  .page-toast-wrapper {
    padding: 0 20px;
    position: absolute;
    top: 50%;
    width: 100%;
    transform: translateY(-50%);

    button:not(:last-child) {
      margin-bottom: 20px;
    }
  }
</style>
