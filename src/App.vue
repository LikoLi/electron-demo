<template>
  <div id="app">
    <el-menu :default-active="activeIndex" class="el-menu-demo" mode="horizontal">
      <el-menu-item index="1">OMS异常分析平台</el-menu-item>
    </el-menu>
    <div class="sor-content">
      <el-form :inline="true" :model="formInline" class="demo-form-inline sor-search">
        <el-form-item label="异常编号">
          <el-input v-model="formInline.user" placeholder="异常编号"></el-input>
        </el-form-item>
        <el-form-item>
          <el-button type="primary" @click="onSubmit">查询</el-button>
        </el-form-item>
      </el-form>
      <el-table :data="tableData" stripe border fit style="width: 100%">
        <el-table-column prop="code" label="异常编号" width="180"></el-table-column>
        <el-table-column prop="desc" label="异常描述" width="240"></el-table-column>
        <el-table-column prop="solution" label="解决方案"></el-table-column>
        <el-table-column prop="option" label="关联操作"></el-table-column>
      </el-table>
      <el-pagination background layout="prev, pager, next" :total="1000" class="sor-pagination"></el-pagination>
    </div>
  </div>
</template>

<script>
// import HelloWorld from './components/HelloWorld.vue'

export default {
  name: 'app',
  data: function() {
      return { 
        tableData: [{
          code: 'OMS-00001',
          desc: '委托状态为【10】不允许修改',
          solution: '该委托已经进行了EOD处理, 不允许进行修改操作, 请等待EOD操作完成后重新下达委托测试。关于EOD是否完成，请咨询相关测试。',
          option: "https://www.baidu.com"
        }, {
          code: 'OMS-00002',
          desc: '委托状态为【10】不允许修改',
          solution: '该委托已经进行了EOD处理, 不允许进行修改操作, 请等待EOD操作完成后重新下达委托测试。关于EOD是否完成，请咨询相关测试。',
          option: "https://www.baidu.com"
        }, {
          code: 'OMS-00003',
          desc: '委托状态为【10】不允许修改',
          solution: '该委托已经进行了EOD处理, 不允许进行修改操作, 请等待EOD操作完成后重新下达委托测试。关于EOD是否完成，请咨询相关测试。',
          option: "https://www.baidu.com"
        }, {
          code: 'OMS-00004',
          desc: '委托状态为【10】不允许修改',
          solution: '该委托已经进行了EOD处理, 不允许进行修改操作, 请等待EOD操作完成后重新下达委托测试。关于EOD是否完成，请咨询相关测试。',
          option: "https://www.baidu.com"
        }, {
          code: 'OMS-00005',
          desc: '委托状态为【10】不允许修改',
          solution: '该委托已经进行了EOD处理, 不允许进行修改操作, 请等待EOD操作完成后重新下达委托测试。关于EOD是否完成，请咨询相关测试。',
          option: "https://www.baidu.com"
        }],
        formInline: {
          user: '',
          region: ''
        },
        activeIndex: '1'
      }
    },
    methods: {
      onSubmit() {
        console.log('submit!');
      }
    },
    mounted() {
      axios.get('https://www.runoob.com/try/ajax/json_demo.json')
          .then(response => console.log('success:' + response))
          .catch(function(error) {
            console.log(error);
          });
    }
}
</script>

<style>
.sor-search {
  float: right;
  margin-top: 20px;
}

.sor-pagination {
  text-align: center;
  margin-top: 20px;
}

.sor-content {
  width: 80%;
  margin: 0 auto;
}
</style>
