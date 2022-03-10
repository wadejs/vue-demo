<template>
  <div id="app">
    <button @click="setCount">click</button>
    <h1>{{count}}</h1>
    <Test data="123" />
    <HelloWorld msg="Welcome to Your Vue.js App" />
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
// import Test from './components/Test.vue'
const Test = {
  data () {
    return {
    }
  },
  computed: {
    params () {
      return {
        attrs: this.$attrs
      }
    }
  },
  render (h) {
    console.log('render')
    // console.log(this.params.attrs.data)
    return h(
      'div',   // 标签名称
      this.$attrs.data
    )
  }
}
export default {
  name: 'App',
  components: {
    HelloWorld,
    Test
  },
  data () {
    return {
      count: 0
    }
  },
  methods: {
    setCount () {
      setInterval(() => {
        this.count++
      }, 100)
    }
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
