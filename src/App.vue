<template>
  <div>
    <van-nav-bar left-arrow title="xxxxxxxxxx" fixed @click-left="onClickLeft" />
    <img
      class="user-poster"
      src="https://img.yzcdn.cn/public_files/2017/10/23/8690bb321356070e0b8c4404d087f8fd.png"
    />
    <van-row class="user-links">
      <van-col span="8">
        <van-circle
          layer-color="#ebedf0"
          v-model="currentRate1"
          :rate="currentRate1"
          :speed="100"
          :text="text1"
        />
        <p>繁荣度</p>
      </van-col>
      <van-col span="8">
        <van-circle
          layer-color="#ebedf0"
          v-model="currentRate2"
          :rate="currentRate2"
          :speed="100"
          :text="text2"
        />
        <p>稳定度</p>
      </van-col>
      <van-col span="8">
        <van-circle
          layer-color="#ebedf0"
          v-model="currentRate3"
          :rate="currentRate3"
          :speed="100"
          :text="text3"
        />
        <p>民心</p>
      </van-col>
    </van-row>

    <van-grid :column-num="3">
  <van-grid-item
    v-for="value in 6"
    :key="value"
    icon="photo-o"
    text="文字"
  />
</van-grid>

    <van-cell-group>
      <van-cell icon="points" title="我的积分" is-link />
      <van-cell icon="gold-coin-o" title="我的优惠券" is-link />
      <van-cell icon="gift-o" title="我收到的礼物" is-link />
    </van-cell-group>

    <van-tabbar v-model="active">
      <van-tabbar-item name="home" icon="home-o">标签</van-tabbar-item>
      <van-tabbar-item name="search" icon="search">标签</van-tabbar-item>
      <van-tabbar-item name="friends" icon="friends-o">标签</van-tabbar-item>
      <van-tabbar-item name="setting" icon="setting-o">设置</van-tabbar-item>
    </van-tabbar>
  </div>
</template>

<script>
import { Toast } from "vant";
export default {
  methods: {
    onClickLeft() {
      Toast("返回");
    }
  },
  computed: {
    text1() {
      return this.currentRate1.toFixed(0) + "%";
    },
    text2() {
      return this.currentRate2.toFixed(0) + "%";
    },
    text3() {
      return this.currentRate3.toFixed(0) + "%";
    }
  },
  data() {
    return {
      active: "home",
      currentRate1: 30,
      currentRate2: 50,
      currentRate3: 70
    };
  }
};
</script>

<style lang="less">
.user {
  &-poster {
    width: 100%;
    height: 53vw;
    display: block;
  }
  &-group {
    margin-bottom: 15px;
  }
  &-links {
    padding: 15px 0;
    font-size: 12px;
    text-align: center;
    background-color: #fff;
    .van-icon {
      display: block;
      font-size: 24px;
    }
  }
}
</style>
