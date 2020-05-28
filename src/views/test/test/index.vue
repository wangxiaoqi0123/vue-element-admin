<template>
  <div class="container">
    <el-card
      class="box-card"
      shadow="never"
    >
      <el-tabs v-model="activeName">
        <el-tab-pane
          label="Loading效果"
          name="roles"
        >
          <Loading />
        </el-tab-pane>
        <el-tab-pane
          label="测试"
          name="nodes"
        >
          <el-button
            type="primary"
            @click="onToast"
          >按钮Toast</el-button>
          <el-button
            type="primary"
            @click="onIndicator"
          >按钮Indicator</el-button>
        </el-tab-pane>
        <el-tab-pane
          label="测试"
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
import Loading from './modules/Loading'
export default {
  components: {
    Loading
  },
  data() {
    const item = {
      date: '2016-05-02',
      name: '王小虎',
      address: '上海市普陀区金沙江路 1518 弄'
    }
    return {
      tableData: Array(20).fill(item),
      activeName: 'roles',
      num: '0'
    }
  },
  computed: {},
  watch: {},
  mounted() { },
  methods: {
    onToast() {
      this.$Toast({ message: 'Toast...' })
    },
    onIndicator() {
      this.$Indicator()
      setTimeout(() => {
        this.$Indicator.hidden()
      }, 5000)
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
