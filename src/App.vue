<template>
  <div id="app">
    <Jumbotron :api="api"/>
    <div class="main-blocks" :key="block" v-for="block in api.blocks">
      <Block :api="block" />
    </div>
    <Footer :api="api"/>
  </div>
</template>

<script>
import axios from 'axios'

import Jumbotron from './components/Jumbotron.vue'
import Block from './components/Block.vue'
import Footer from './components/Footer.vue'

export default {
  name: 'app',
  components: {
    Jumbotron,
    Block,
    Footer
  },
  data () {
    return {
      api: null
    }
  },
  mounted () {
    axios
      .get('https://wolfgangalmeida.pythonanywhere.com/api/website/')
      .then(response => (this.api = response.data))
  }
}
</script>

<style>
</style>
