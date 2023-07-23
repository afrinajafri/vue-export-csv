<template>
   <img alt="Vue logo" class="logo" src="./assets/logo.svg" width="125" height="125" />
  <ExpCSV msg="Welcome to Your Vue.js App"/>
</template>

<script>
import ExpCSV from './components/ExpCSV.vue' 
import 'bootstrap/dist/css/bootstrap.css';
export default {
  name: 'App',
  components: {
    ExpCSV
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>
