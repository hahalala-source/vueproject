

子组件：

<template>
<div>
  <button @click="getParentValue()">获取父组件的属性的值</button>
    <button @click="getParentMethod()">获取父组件的方法</button>
</div>
</template>
<script>
export default {
  name: 'son',
    methods: {
    getParentValue () {
      alert(this.$parent.msg)  //调用子组件的值，弹窗显示
    },
    getParentMethod () {
      this.$parent.run()  //调用子组件的方法
    }
  }
}
</script>

分析：

    通过使用this.$parent ,子组件可以直接使用父组件的 值 和 函数
         this.$parent.msg   获取到父组件的值（msg存放的数据）
         this.$parent.run()  获取夫组件中的逻辑方法，并返回其逻辑内容



父组件：

<template>
  <div id="app">
<!--    <img src="./assets/logo.png">-->
    <son></son>
    <router-view/>
  </div>
</template>

<script>
import son from './components/son'
export default {
  name: 'App',
  data: function () {
    return {
      msg:"哈喽，我是父组件的值！我过来啦"
    }
  },
  components: {
    son
  },
  methods:{
     run(){
          console.log("哈哈哈，父组件的方法来啦，迎接哟！")
     }
  }
}
</script>



演示效果：

    点击按钮 ==》 获取父组件的属性的值  -----  弹窗显示  ----  哈喽，我是父组件的值！我过来啦
    点击按钮 ==》 获取父组件的方法     -----   打印显示  ----  哈哈哈，父组件的方法来啦，迎接哟！





















