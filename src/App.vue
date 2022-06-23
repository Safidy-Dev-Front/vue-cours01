
<template>
  <img alt="Vue logo" src="./assets/logo.png">
  <HelloWorld msg="Welcome to Your Vue.js App"/>
  <FirstComponent :value="greeting"/>
  <ReactivityComponent />
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import FirstComponent from './components/FirstComponent.vue'
import ReactivityComponent from '@/components/Reactivity.vue'

export default {
  name: 'App',
  data() {
    return {
      greeting: "coucou le monde"
    }
  },
  components: {
    HelloWorld, 
    FirstComponent,
    ReactivityComponent
  }
}
</script>

<style lang="scss">
// @import '@/assets/sass/main.scss';
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
  // background-color: red;
}
</style>
