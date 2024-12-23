
<template>
  <div id="app" class="app-container">
    <nav-body :style="style.navStyle"></nav-body>
    <social-body :style="style.socialStyle"></social-body>
    <main-body></main-body>
  </div>
</template>

<script>
import main from './components/main.vue'
import nav from './components/nav.vue'
import social from './components/social.vue'

let navStyle = {
  float: 'left',
  width: '260px',
  height: '100%',
  overflow: 'auto'
}
let socialStyle = {
  float: 'right',
  width: '280px',
  height: '100%',
  overflow: 'auto'
}

export default {
  name: 'App',
  data() {
    return {
      style: {
        navStyle,
        socialStyle
      }
    }
  },
  components: {
    'main-body': main,
    'nav-body' : nav,
    'social-body': social
  }
}
</script>

<style>
.app-container {
  overflow: hidden;
  margin: 0 auto;
  max-width: 1600px;
  height: 100vh;
}
</style>
