<template>
  <div class='his-product'>
    <el-table :data="tableData" :span-method="objectSpanMethod" style="width: 100%;margin-bottom: 20px;" row-key="id"
      border default-expand-all>
      <el-table-column prop="year" label="年份" width="180">
      </el-table-column>
      <el-table-column prop="date" label="发布日期">
      </el-table-column>
      <el-table-column prop="model" label="型号">
      </el-table-column>
      <el-table-column prop="type" label="产品类别">
      </el-table-column>
      <el-table-column prop="features" label="新特性">
      </el-table-column>
    </el-table>
    <div v-for="item in tableData">
      <el-table :data="tableData1" style="width: 100%" row-key="id" border lazy :load="load"
        :tree-props="{ children: 'children', hasChildren: 'hasChildren' }">
        <el-table-column prop="year" label="年份" sortable width="180">
        </el-table-column>
        <el-table-column prop="date" label="日期" sortable width="180">
        </el-table-column>
        <el-table-column prop="name" label="姓名" width="180">
        </el-table-column>
        <el-table-column prop="address" label="地址">
        </el-table-column>
      </el-table>
    </div>

  </div>
</template>

<script>
export default {
  data() {
    return {
      tableData: [{
        id: '2020',
        year: '2020',
        date: '1月1日',
        model: 'iPhone 12',
        type: '手机',
        features: '全新设计'
      }, {
        id: '2021',
        year: '2021',
        date: '1月1日',
        model: 'iPhone 12',
        type: '手机',
        features: '全新设计'
      }, {
        id: '2022',
        year: '2022',
        date: '1月1日',
        model: 'iPhone 12',
        type: '手机',
        features: '全新设计'
      },],
      tableData1: [{
        id: 1,
        date: '2016-05-02',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1518 弄'
      }, {
        id: 2,
        date: '2016-05-04',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1517 弄'
      }, {
        id: 3,
        date: '2016-05-01',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1519 弄',
      }, {
        id: 4,
        date: '2016-05-03',
        name: '王小虎',
        address: '上海市普陀区金沙江路 1516 弄'
      }]
    }
  },
  methods: {
    load(tree, treeNode, resolve) {
      setTimeout(() => {
        resolve([
          {
            id: 31,
            date: '2016-05-01',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1519 弄'
          }, {
            id: 32,
            date: '2016-05-01',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1519 弄'
          }
        ])
      }, 1000)
    },
    /**
    * @description: 合并列
    * @param {type} 
    * @return: 
    */
    objectSpanMethod({ row, column, rowIndex, columnIndex }) {
      if (columnIndex === 0) {
        if (rowIndex % 2 === 0) {
          return {
            rowspan: 2,
            colspan: 1
          };
        } else {
          return {
            rowspan: 0,
            colspan: 0
          };
        }
      }
    }
  },
}
</script>

<style lang='less'>
</style>

