<template>
  <div id="app" v-if="loaded">
    <Jumbotron :api="api"/>
    <div class="main-blocks" :key="block.id" v-for="block in api.blocks">
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

import { websiteDefaults, backendAddress } from './defaults/defaults.js'

export default {
  name: 'app',
  components: {
    Jumbotron,
    Block,
    Footer
  },
  data () {
    return {
      api: websiteDefaults,
      loaded: false
    }
  },
  mounted () {
    axios
      .get(backendAddress.PROD + '/api/website/')
      .then(response => {
          this.api = response.data
          this.loaded = true
        }, () => {
          this.api = websiteDefaults
          this.loaded = true
        }
      )
  }
}
</script>

<style>
</style>
