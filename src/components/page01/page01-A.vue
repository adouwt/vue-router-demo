<template>
  <div>
    <h2 class="text-center">{{title}}</h2>
    <input v-model="why">
    <h3>{{why}}</h3>
    <button @click="getData">看看人家是怎么过来的</button>
    <h3>下面显示a.txt的内容</h3>
    <h2 id="h2" >{{arr}}</h2>
    <router-view></router-view>
  </div>
</template>

<script>
export default {
  name: 'page01-a',
  data () {
    return {
      title: '这里是第二个下的子页面',
      why: '有什么感想',
      arr: ''
    }
  },
  methods: {
    getData: function () {
      this.$http.get('./static/a.php').then((response) => {
        console.log(response.data)
        this.arr += response.data + '\n'
      }, function (err) {
        alert('错误：' + err.data)
      })
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
  .spacing li:hover {
    background-color: #005aa0;
    color: #fff;
    cursor: pointer;
  }
</style>
