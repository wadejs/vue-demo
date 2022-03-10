<template>
  <div class="hello">
    <h1>{{ msg }}</h1>
    <div class="wrapper" ref="wrapper">
      <div v-for="item in list" :key="item">{{item}}</div>
    </div>
  </div>
</template>

<script>
export default {
  name: 'HelloWorld',
  props: {
    msg: String
  },
  data () {
    return {
      obj: {},
      list: Array.from({length: 10}).map((itme, i) => {
        return i
      })
    }
  },
  mounted () {
    console.log('test')
    console.log(this.obj?.a?.c?.test())
    this.fetchData().then(res => {
      console.log(res)
      this.list = res.data
      console.log(this.$refs.wrapper.offsetHeight)
    }).then(() => {
      console.log(this.$refs.wrapper.offsetHeight)
      this.$nextTick(() => {
        console.log(this.$refs.wrapper.offsetHeight)
      })
    })
  },
  methods: {
    fetchData () {
      return new Promise((resolve) => {
        setTimeout(() => {
          resolve({data: Array.from({length: 20}).map((itme, i) => {
        return i
      })})
        }, 1000);
      })
    }
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
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
