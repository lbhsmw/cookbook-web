<template>
  <div class="dashboard-container">
    <div class="dashboard-text">name: {{ name }}</div>
    <div>就直接从这里开始吧！！！fighting</div>
    <el-button type="primary" @click="firstClickFuction">我是一个按钮</el-button>
  </div>
</template>

<script>
import axios from 'axios'
import {mapGetters} from 'vuex'

export default {
  name: 'Dashboard',
  computed: {
    ...mapGetters([
      'name'
    ])
  },
  data() {
    return {
      message: 'Hello Vue.js!'
    }
  },
  methods: {
    firstClickFuction: function() {
    /*  this.$message('这是一条消息提示')*/
      axios.get('http://localhost:8080/').then(response => {
        this.$message(response.data)
      })
    }
  }
}
</script>

<style lang="scss" scoped>
.dashboard {
  &-container {
    margin: 30px;
  }

  &-text {
    font-size: 30px;
    line-height: 46px;
  }
}
</style>
