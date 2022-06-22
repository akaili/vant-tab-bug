<template>
  <div id="app">
    <p>最后一个选中时文字颜色相对其他比较浅</p>
    <van-tabs v-model="active">
      <van-tab v-for="item in tabs.filter((item, index) => index < 6)" :key="item.id" :title="item.name"></van-tab>
    </van-tabs>

    <p>正常情况1</p>
    <van-tabs v-model="active">
      <van-tab v-for="item in tabs" :key="item.id" :title="item.name"></van-tab>
    </van-tabs>
  </div>
</template>

<script>
import list from './data.json';

export default {
  name: 'App',
  data() {
    return {
      active: '',
      tabs: list,
    };
  },
};
</script>

<style lang="less">
@Regular: 'SourceHanSansCN-Regular';
@Medium: 'SourceHanSansCN-Medium';
@Bold: 'SourceHanSansCN-Bold';

#app {
  height: 100vh;
  background-color: #f2f2f2;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  padding: 20px 14px;
}

.van-tabs__wrap {
  height: 30px;
  overflow: hidden;
  border-radius: 6px;
}

.van-tab__text {
  color: #333;
  font-size: 13px;
  font-family: @Regular;
  -webkit-tap-highlight-color: transparent;
}

.van-tab--active {
  .van-tab__text {
    color: #f5759a;
    font-weight: bold;
    font-size: 14px;
    -webkit-tap-highlight-color: transparent;
  }
}

.van-tabs__line {
  width: 30px;
  height: 6px;
  // margin-bottom: -3px;
  background-color: #f5759a !important;
}
</style>
