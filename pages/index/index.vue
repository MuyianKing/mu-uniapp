<template>
  <cu-custom bgColor="bg-gradual-blue" :isBack="true">
    <block slot="backText">返回</block>
    <block slot="content">导航栏</block>
  </cu-custom>
</template>

<script>
  export default {
    data() {
      return {
        title: 'Hello'
      }
    },
    onLoad() {
      this.getLocation()

    },
    methods: {
      getWeather() {

      },
      getLocation() {
        this.common.promisify('getLocation', {
          type: 'wgs84'
        }).then(res => {
          console.log(res)
        })
      }
    }
  }
</script>

<style>
  .content {
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: center;
  }

  .logo {
    height: 200rpx;
    width: 200rpx;
    margin-top: 200rpx;
    margin-left: auto;
    margin-right: auto;
    margin-bottom: 50rpx;
  }

  .text-area {
    display: flex;
    justify-content: center;
  }

  .title {
    font-size: 36rpx;
    color: #8f8f94;
  }
</style>
