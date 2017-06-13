<template>
  <div>
    <div class="home text-center">{{home}}</div>
    <div id="app2">
      <div>
        <el-button @click="show = !show">Click Me</el-button>

        <div style="display: flex; margin-top: 20px; height: 100px;">
          <transition name="el-fade-in-linear">
            <div v-show="show" class="transition-box">
              <span>.el-fade-in-linear </span>
              <p>ele的样式 </p>
            </div>
          </transition>
          <transition name="el-fade-in">
            <div v-show="show" class="transition-box">
              <span>.el-fade-in</span>
              <p>ele的样式 </p>
            </div>
          </transition>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
  export default {
    name: 'home',
    data () {
      return {
        home: 'index.js是配置所有路由，包括多级路由，通过父组件下定义children',
        show: true
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
  .transition-box {
    margin-bottom: 10px;
    width: 200px;
    height: 100px;
    border-radius: 4px;
    background-color: #20A0FF;
    text-align: center;
    color: #fff;
    padding: 40px 20px;
    box-sizing: border-box;
    margin-right: 20px;
  }
</style>
