<template>
  <div id="app">
    <router-view/>
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

<style>
#app {
  font-family: "Avenir", Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
