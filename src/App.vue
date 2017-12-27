<template>
  <div id="app">
    <img src="./assets/logo.png">
    <div>
      {{ buyType.label }} - {{ buyType.value}}
    </div>
    <div>
        <Selection :selections="buyTypes" @on-change="onParamChange('buyType', $event)"></Selection>
    </div>
    <!-- <HelloWorld/> -->
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld'
import Selection from './components/base/selection'

export default {
  name: 'app',
  data () {
    return {
      buyType: {},
      buyTypes: [
        {
          label: '入門版',
          value: 0
        },
        {
          label: '中級版',
          value: 1
        },
        {
          label: '高級版',
          value: 2
        }
      ]
    }
  },
  components: {
    // HelloWorld,
    Selection
  },
  methods: {
    onParamChange (attr, val) {
      this[attr] = val
      console.log(attr)
      console.log(val)
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
