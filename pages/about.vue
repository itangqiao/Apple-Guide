<template>
  <div>
    <el-button>about</el-button>
    
    <el-table :data="data" border stripe>
      <el-table-column v-for="col in columns"  :key="col.id" :label="col.label" :width="col.width">
      </el-table-column>
    </el-table>

  </div>
</template>
<script>
export default {
  data() {
    return {
      data: [{ a: 1 }],
      columns: [
        { id: 1, label: "1", width: 100 },
        { id: 2, label: "2", width: 100 }
      ],
    }
  }
}
</script>
<style>
</style>