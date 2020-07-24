<template>
<div class="divfirst">
  <span> {{ mess }} </span>
  <h1> {{ bindMsg }}   </h1>
  <button @click="run()">点击调用父组件方法</button>
  <button @click="getPrasent()">点击获取父组件实体</button>
</div>
</template>

<script>
export default {
  name: 'son',
  props: {
    'mess': String,
    'bindMsg': [String, Number],
    'run': Function,
    'fatherThis': Object
  },
  data () {
    return {}
  },
  methods: {
    getPrasent () {
      this.fatherThis.run()
      alert(this.fatherThis.msg)
    }
  }
}
</script>
<style scoped>
</style>
