<template>
  <div class="container">
    <el-card
      class="box-card"
      shadow="never"
    >
      <el-tabs v-model="activeName">
        <el-tab-pane
          label="角色"
          name="roles"
        >
          <el-button type="primary">
            编辑
          </el-button>
          <el-button type="primary">
            新增
          </el-button>
          <br>
          <br>
          <br>
          <br>
          <br>
        </el-tab-pane>
        <el-tab-pane
          label="节点"
          name="nodes"
        >
          <el-container>
            <el-main style="padding:0">
              <el-table :data="tableData">
                <el-table-column
                  prop="date"
                  label="日期"
                  width="140"
                />
                <el-table-column
                  prop="name"
                  label="姓名"
                  width="120"
                />
                <el-table-column
                  prop="address"
                  label="地址"
                />
              </el-table>
            </el-main>
          </el-container>
        </el-tab-pane>
        <el-tab-pane
          label="流程"
          name="process"
        >
          流程
          <br>
          <br>
          <br>
          <br>
          <br>
        </el-tab-pane>
      </el-tabs>
    </el-card>
  </div>
</template>
<script>
export default {
  data() {
    const item = {
      date: '2016-05-02',
      name: '王小虎',
      address: '上海市普陀区金沙江路 1518 弄'
    }
    return {
      tableData: Array(20).fill(item),
      activeName: 'roles'
    }
  },
  computed: {},
  watch: {},
  mounted() { },
  methods: {
    onHandle() {

    }
  }
}
</script>
<style lang='scss' scoped>
.container {
  padding: 20px;
}

.box {
  width: 200px;
  height: 50px;
  border: 1px solid #000;
}
</style>
