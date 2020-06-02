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
            v-debounce="{fun: 'handleDblclick', event: 'click', wait: 500}"
            :loading="loading"
            type="primary"
          >防抖v-debounce</el-button>
          <el-button
            v-throttle="{fun: 'handleDblclick', event: 'click',wait: 1000}"
            :loading="loading"
            type="primary"
          >节流v-throttle</el-button>
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
      num: '0',
      loading: false
    }
  },
  computed: {},
  watch: {},
  mounted() { },
  methods: {
    onToast() {
      this.$Toast({ message: 'Toast...' })
    },
    handleDblclick() {
      // this.loading = true
      console.log('111 :>> ', 111)
      setTimeout(() => {
        this.loading = false
      }, 1000)
      console.log('222 :>> ', 222)
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
