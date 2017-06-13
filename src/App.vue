<template>
  <div>
    <h3>首页导航栏</h3>
    <div>
      <el-menu theme="dark" :default-active="activeIndex" class="el-menu-demo" mode="horizontal" @select="handleSelect">
        <el-menu-item index="1"><a href="/">处理中心</a></el-menu-item>
        <el-submenu index="2">
          <template slot="title">我的工作台</template>
          <el-menu-item index="2-1">选项1</el-menu-item>
          <el-menu-item index="2-2">选项2</el-menu-item>
          <el-menu-item index="2-3">选项3</el-menu-item>
        </el-submenu>
        <el-menu-item index="3"><a href="" >订单管理</a></el-menu-item>
        <el-menu-item index="4"><a href="" >第三个</a></el-menu-item>
        <el-menu-item index="5"><a href="" >第四个</a></el-menu-item>
      </el-menu>
    </div>
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
        ],
        activeIndex: '1',
        activeIndex2: '1'
      }
    },
    methods: {
      handleSelect (key, keyPath) {
        console.log(key, keyPath)
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
