<template>
  <div class="header">
    <div class="header-icon" v-show="backDisplay" @click="goBack"><i class="icon"><img  class="imgs" src="../assets/images/back.png"></i></div>
    <div class="header-cont" :class="{ 'pad-l': !backDisplay }"><p>{{title}}</p></div>
    <div class="header-icon" v-show="menuDisplay" @click="showBar"><i class="icon">&#xe634;</i></div>
    <div class="header-icon" v-show="mapDisplay" @click="getMap"><i class="icon map-icon">&#xe600;</i></div>
  </div>
</template>

<script>
export default {
  props: {
    title: String,
    menuDisplay: Boolean,
    backDisplay: Boolean,
    mapDisplay: Boolean
  },
  data() {
    return {};
  },
  methods: {
    goBack() {
      window.history.back();
    },
    getMap() {
      alert("开发中");
    },
    showBar() {
      this.$store.dispatch("setNavState", true);
    }
  }
};
</script>

<style lang="scss" scoped>
@import "../assets/css/function";
.imgs{
  width:17px;
  height: 17px;
}
.header {
  position: fixed;
  transform: translateZ(0);
  top: 0;
  z-index: 4;
  height: px2rem(100px);
  width: 100%;
  background: #d4260b;
  display: flex;
  flex-direction: row;
  .header-icon {
    flex: 1;
    text-align: center;
    > i {
      line-height: px2rem(100px);
    }
    .map-icon {
      font-size: 22px;
    }
  }

  .header-cont {
    flex: 6;
    > p {
      line-height: px2rem(100px);
      color: #ffffff;
      font-size: 17px;
    }
  }
  .pad-l {
    padding-left: px2rem(40px);
  }
}
</style>