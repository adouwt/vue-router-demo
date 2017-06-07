<template>
  <div>
    <div class="home text-center">{{home}}</div>
  </div>
</template>

<script>
  export default {
    name: 'home',
    data () {
      return {
        home: 'index.js是配置所有路由，包括多级路由，通过父组件下定义children'
      }
    },
    components: {}
  }
</script>

<style>
  .home {
    font-size: 2.4em;
    font-weight: bold;
  }
</style>
