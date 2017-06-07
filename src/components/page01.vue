<template>
  <div>
    <h2 class="text-center">{{title}}</h2>
    <ul class="text-center spacing" style="padding: 0">
      <li v-for="item in links"><a @click="$goRoute(item.route)">{{item.text}}</a></li>
    </ul>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'page01',
  data () {
    return {
      title: '这里是第二个页面',
      links: [
        {
          text: '失恋了',
          route: '/page01/page01-a'
        },
        {
          text: '又拱小白菜了',
          route: '/page01/page01-b'
        }
      ]
    }
  }
}
</script>
<style type="text/css">
  .spacing li {
    display: inline-block;
    padding: 10px;
    background-color: #ddd;
    margin-right: 30px;
    border-radius: 3px;
    transition: background-color .5s;
  }
  .home-nav li:hover {
    background-color: #005aa0;
    color: #fff;
    cursor: pointer;
  }
</style>
