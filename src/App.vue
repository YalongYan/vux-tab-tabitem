<template>
  <div id="app">
    <img src="./assets/logo.png">
      <tab line-width="2">
       <tab-item selected @on-item-click="onItemClick">已发货</tab-item>
       <tab-item @on-item-click="onItemClick">未发货</tab-item>
       <tab-item @on-item-click="onItemClick">全部订单</tab-item>
     </tab>
    <tab bar-active-color="red" :line-width="1">
      <tab-item>已发货</tab-item>
      <tab-item selected>未发货</tab-item>
      <tab-item>全部订单</tab-item>
      <tab-item>全部订单</tab-item>
      <tab-item>全部订单</tab-item>
    </tab>
    <tab :scroll-threshold="5">
      <tab-item v-for="n in 8" :key="n" :selected="n===1">已发货{{ n }}</tab-item>
    </tab>
  </div>
</template>

<script>
import {Tab, TabItem} from './components/tab/index.js'
// import {Tab, TabItem}  from 'vux'
export default {
  name: 'app',
  data () {
    return {
      msg: 'Welcome to Your Vue.js App'
    }
  },
  components: {
    Tab,
    TabItem
  },
  methods: {
    onItemClick (index) {
      console.log('on item click:', index)
    }
  }
}
</script>
 
<style lang="scss">
body , html{
  padding: 0;
  margin: 0;
}
.vux-center-v, .vux-center-h, .vux-center {
  display: flex;
}

.vux-center-v, .vux-center {
  align-items: center;
}

.vux-center-h, .vux-center {
  justify-content: center;
}
body, html{
    height: 100%;
    width: 100%;
    overflow-x: hidden;
}
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

h1, h2 {
  font-weight: normal;
}

ul {
  list-style-type: none;
  padding: 0;
}

li {
  display: inline-block;
  margin: 0 10px;
}

a {
  color: #42b983;
}
</style>
