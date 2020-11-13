<template>
  <div id="app">
    <home></home>
  </div>
</template>

<script>
import Home from './components/Home.vue';
import Test from './components/test.vue'
export default {
  name: 'App',
  components: {
    Home,
    Test
  }
}
</script>

<style>
p {
  font-size: 30px;
  color: red;
}
</style>
