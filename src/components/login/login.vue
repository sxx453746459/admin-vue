<template>
<div>
  <p>登陆组件</p>
  <form @submit.prevent="login">
    <div>
      <label for="username">用户名</label>
      <input
        type="text"
        id="username"
        v-model="userForm.username">
    </div>
    <div>
      <label for="password">密码</label>
      <input
        type="password"
        id="password"
        v-model="userForm.password">
    </div>
    <div>
      <button>点击登陆</button>
    </div>
  </form>
</div>
</template>

<script>
export default {
  data () {
    return {
      userForm: {
        username: '',
        password: ''
      }
    }
  }
}
</script>

<style>
</style>
