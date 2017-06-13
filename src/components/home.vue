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
    <hr>
    <div class="">
      <el-row :gutter="20">
        <el-col :span="12">
          <el-table
            :data="tableData2"
            style="width: 100%"
            :row-class-name="tableRowClassName">
            <el-table-column
              prop="date"
              label="日期"
              width="180">
            </el-table-column>
            <el-table-column
              prop="name"
              label="姓名"
              width="180">
            </el-table-column>
            <el-table-column
              prop="address"
              label="地址">
            </el-table-column>
          </el-table>
        </el-col>
      </el-row>
    </div>
    <div class="block">
     <span class="demonstration">完整功能</span>
     <el-pagination @size-change="handleSizeChange" @current-change="handleCurrentChange" :current-page="currentPage4" :page-sizes="[100, 200, 300, 400]" :page-size="100" layout="total, sizes, prev, pager, next, jumper" :total="400">
     </el-pagination>
    </div>
  </div>
</template>

<script>
  let addressM = '上海市普陀区金沙江路 1518 弄'
  export default {
    name: 'home',
    data () {
      return {
        home: 'index.js是配置所有路由，包括多级路由，通过父组件下定义children',
        show: true,
        currentPage4: 4,
        tableData2: [{
          date: '2016-05-02',
          name: '王小虎',
          address: addressM
        }, {
          date: '2016-05-04',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-01',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }, {
          date: '2016-05-03',
          name: '王小虎',
          address: '上海市普陀区金沙江路 1518 弄'
        }]
      }
    },
    methods: {
      handleSizeChange (val) {
        console.log(`每页 ${val} 条`)
      },
      handleCurrentChange (val) {
        console.log(`当前页: ${val}`)
      },
      tableRowClassName (row, index) {
        if (index === 1) {
          return 'info-row'
        } else if (index === 3) {
          return 'positive-row'
        }
        return ''
      }
    }
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
  .el-table .info-row {
    background: #c9e5f5;
  }

  .el-table .positive-row {
    background: #e2f0e4;
  }
</style>
