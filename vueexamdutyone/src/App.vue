<template>
  <div id="app">
<!--    <img src="./assets/logo.png">-->
    <son mess="父组件给子组件传值了"  :bindMsg = "msg" :run = "run" :fatherThis="this"></son>
    <router-view/>
  </div>
</template>

<script>
import son from './components/son'
export default {
  name: 'App',
  data: function () {
    return {
      title: ' ',
      msg: '大兄弟，脚下抹油，咱溜啦'
    }
  },
  components: {
    son
  },
  methods: {
    run () {
      console.log('兄弟啊，跑路啦！')
    }

  }

}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
