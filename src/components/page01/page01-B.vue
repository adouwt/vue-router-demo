<template>
  <div>
    <h3 class="text-center red">不知道什么是白菜</h3>
    <ul class="text-center spacing" style="padding: 0">
      <li v-for="item in links"><a @click="$goRoute(item.route)">{{item.text}}</a></li>
    </ul>
    <router-view></router-view>
  </div>
</template>

<script>
  export default {
    name: '',
    data () {
      return {
        links: [
          {
            text: '白菜是新鲜的意思',
            route: '/page01/page01-b/end'
          },
          {
            text: '懂了',
            route: '/page01/page01-b/ok'
          },
          {
            text: '回家了',
            route: '/home'
          }
        ]
      }
    }
  }
</script>
