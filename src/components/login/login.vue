<template>
<div class="login-wrap">
  <el-form label-position="top" ref="form" :model="userForm" label-width="80px">
    <el-form-item label="用户名">
      <el-input
      v-model="userForm.username"></el-input>
    </el-form-item>
    <el-form-item label="密码">
      <el-input
      type="password"
      v-model="userForm.password"></el-input>
    </el-form-item>
    <el-form-item>
      <el-button
      type="primary"
      @click="login">立即创建</el-button>
    <el-button>取消</el-button>
  </el-form-item>
  </el-form>
</div>
</template>

<script>
import axios from 'axios'

export default {
  data () {
    return {
      userForm: {
        username: '',
        password: ''
      }
    }
  },
  methods: {
    async login () {
      // 1. 采集表单数据
      // 2. 表单验证
      // 3. 发请求执行登陆操作
      // 4. 根据响应做交互
      const res = await axios.post('http://localhost:8888/api/private/v1/login', this.userForm)
      const data = res.data
      if (data.meta.status === 200) {
        this.$router.push({
          name: 'home'
        })
      }
    }
  }
}
</script>

<style>
</style>
