<template>
  <div id="app">
    <!--<HelloWorld msg="Welcome to Your Vue.js App"/>-->
    <Breadboard/>
  </div>
</template>

<script>
//  import VueLazyload from 'vue-lazyload';
import Breadboard from './components/Breadboard.vue';

export default {
  name: 'app',
  components: {
    Breadboard,
  },
};
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
