<template>
  <div class="hello">
    <input v-model="someVar">
    <h1>{{ someVar }}</h1>
  </div>
</template>

<script>
import getRandomString from './getRandomStr.js'

export default {
  name: 'vinput',
  data () {
    return {
      someVar: 'initial value'
    }
  },

  methods: {
    changeSomeVar () {
      let self = this
      setInterval(function () {
        self.someVar = getRandomString()
        console.log(self.someVar)
      }, 10000)
    }
  },

  mounted () {
    this.changeSomeVar()
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
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
