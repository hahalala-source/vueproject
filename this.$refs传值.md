

this.$refs 子组件的值传递到父组件（此外this.$emit也可以  子--》父  传值）


子组件：

<template>
<div>
</div>
</template>

<script>
export default {
  name: 'son',
  data () {
    return {
      msg: '我们是自组件header的值'   //子组件的值
    }
  },
  methods: {
    run () {
      console.log('这是子组件的方法！' + this.msg)  //子组件的方法
    }
  }
}
</script>


解析：
    子组件==值、方法==》1. ref="xxx"  2.this.$refs.xxx.值 | 方法
完成从子组件向父组件的传值。


父组件：

<template>
  <div id="app">
<!--    <img src="./assets/logo.png">-->
    <son ref="header"></son>
    <button @click="getChildValue()">获取子组件的属性的值</button>
    <button @click="getChildMethod()">获取子组件的方法</button>
    <router-view/>
  </div>
</template>

<script>
import son from './components/son'
export default {
  name: 'App',
  data: function () {
    return {
    }
  },
  components: {
    son
  },
  methods: {
    getChildValue () {
      alert(this.$refs.header.msg)  //调用子组件的值，弹窗显示
    },
    getChildMethod () {
      this.$refs.header.run()  //调用子组件的方法
    }
  }
}

// $ref的关键点：
// 1. ref = "header"
// 2. this.$refs.header.数据参数名||函数方法名
// 通信：只要有满足 1 和 2 就可以使父组件调用子组件中的数据和方法，这种情况类似java中的 import 导包

</script>

//父组件点击按钮，触发js事件，函数返回从子组件获取方法和函数==》数据。








