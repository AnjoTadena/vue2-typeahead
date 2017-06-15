<template>
  <div id="app">
      <vue-typeahead 
        placeholder="Search..."
        displayKey="name"
      >
      </vue-typeahead>
  </div>
</template>

<script>
import Typeahead from './Typeahead.vue'

export default {
  name: 'app',
  components: {
    'vue-typeahead': Typeahead
  },
  data () {
    return {
      results: []
    };
  },
  methods: {
    filterItem (key) {
      // this.results = []
      // this.results = this.items.filter((item) => {
      //   return item.indexOf(key) >= 0
      // })
    }
  }
}
</script>

<style lang="scss">
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

.typeahead li{
  display: block;
}
</style>
