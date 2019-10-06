<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <Hello msg="宿泊客の情報を管理しよう"/>
  </div>
</template>

<script>
import Hello from './components/HelloWorld.vue'

export default {
  name: 'app',
  components: {
    Hello
  }
}
</script>

<style>

</style>
