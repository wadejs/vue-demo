<script>
export default {
  functional: true,
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
  render () {
    console.log('render')
    console.log(this.params)
    return (<div>
    <h1>{this.params}</h1>
    </div>)
  }
}
</script>
<style lang='postcss' scoped>
</style>
