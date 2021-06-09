<template>
  <div id="app">
    <Header/>
    <ContenitoreDischi/>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'
import Header from './components/Header'
import ContenitoreDischi from './components/ContenitoreDischi.vue'
export default {
  name: 'App',
  components: {
    Header,
    ContenitoreDischi
  }
}
</script>

<style lang="scss">
  @import './style/general'
</style>
