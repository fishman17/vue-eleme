<template>
  <div id="app">
    <v-header :seller="seller"></v-header>
    <div class="tab border-1px">
      <div class="tab-item">
        <router-link to="/goods">商品</router-link>
      </div>
      <div class="tab-item">
        <router-link to="/ratings">评论</router-link>
      </div>
      <div class="tab-item">
        <router-link to="/seller">商家</router-link>
      </div>
    </div>
    <keep-alive>
      <router-view :seller="seller"></router-view>
    </keep-alive>
  </div>
</template>

<script>
import header from "@/components/header/header.vue";
import axios from 'axios'

const ERR_OK = 0
 
export default {
  data() {
    return {
      seller: {}
    };
  },
  components: {
    "v-header": header
  },
  created() {
    // this.$http.get('api/seller').then((response) => {
    //   response = response.body;
    //   console.log(response)
    // });
    // 获取header组件的数据
    axios.get("api/seller").then(response => {
      console.log(response);
      response = response.data;
      // console.log(response);
      if (response.errno === ERR_OK) {
        this.seller = response.data;
        console.log(this.seller)
        // console.log(this.seller.avatar)
      }
      // console.log(response)
    });
  }
};
</script>

<style scoped lang="stylus">
  @import "./common/stylus/mixin.styl"
  #app
    .tab
      display flex
      width 100%
      height 40px
      line-height 40px
      border-1px(rgba(7,17,27,0.1))
      .tab-item
        flex:1
        text-align center
        & > a
         display block 
         color rgb(77,85,93)
         font-size 14px
         &.active
          color rgb(240,20,20)
</style>
