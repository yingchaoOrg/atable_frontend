<template>
  <div>
    <h1>
      Home {{isCollapse}}
    </h1>

    <el-aside v-if="isCollapse" :style="asideStyle2" style="background-color: rgb(35,63,109)">

    </el-aside>

    <el-main style="height:100%;overflow:scroll">
      <el-table :data="tableData">
        <el-table-column prop="date" label="日期" width="140">
        </el-table-column>
        <el-table-column prop="name" label="姓名" width="120">
        </el-table-column>
        <el-table-column prop="address" label="地址">
        </el-table-column>
      </el-table>
    </el-main>

  </div>
</template>

<script>
export default {
  name: "pages_home",
  data(){
    return {

    }
  },
  props:[
      "isCollapse"
  ]
}
</script>

<style scoped>

</style>
