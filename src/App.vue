<template>
  <div>
    <nav>
        <ul>
            <li><router-link to="/home"></router-link></li>
            <li><router-link to="/gallery"></router-link></li>
        </ul>
    </nav>
  </div>
</template>

<script>
import home from './components/home'
import gallery from './components/gallery'
import Vue from 'vue'
import VueRouter from 'vue-router'

// Enable plugins
Vue.use(VueRouter);

export default {
  name: 'App',
  data() {
    return {
      
    }
  },
  components: {
    home,
    gallery
  },
  methods: {

  },
  routes: [
    { path: '/gallery', component: home },
    { path: '/gallery', component: gallery }
  ]
}
</script>

<style>
* {
    box-sizing: border-box;
}

body {
    padding: 0;
    margin: 0;
    font-family: 'Roboto', sans-serif;
}
</style>