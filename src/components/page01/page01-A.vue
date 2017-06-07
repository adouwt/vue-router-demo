<template>
  <div>
    <h2 class="text-center">{{title}}</h2>
    <h3>{{scald}}</h3>
    <router-view></router-view>
  </div>
</template>

<script>
	export default {
	  name: 'page01-a',
	  data () {
	    return {
	      title: '这里是第二个下的子页面',
	      scald: '为什么会那样的难过'
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
