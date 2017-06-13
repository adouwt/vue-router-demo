<template>
  <div>
    <h3>首页导航栏</h3>
    <ul class="home-nav">
      <li v-for="item in links"><a @click="$goRoute(item.route)">{{item.text}}</a></li>
    </ul>
    <!-- 路由匹配的渲染内容在这里体现 -->
    <router-view></router-view>
  </div>
</template>

<script>
  export default {
    name: 'app',
    data () {
      return {
        links: [
          {
            text: '第一页',
            route: '/home'
          },
          {
            text: '第二页',
            route: '/page01'
          },
          {
            text: '第三页',
            route: '/page02'
          },
          {
            text: '第四页',
            route: '/page03'
          }
        ]
      }
    }
  }
</script>

<style>
  .home-nav li{
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
