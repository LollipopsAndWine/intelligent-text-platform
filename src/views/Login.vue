<template>
  <div class="login">
    <div><small class="text-muted">Kubao Inc.</small></div>
    <div class="avatar">
      <img src="../assets/logo.png" alt="头像">
      <span>酷豹智能文本平台</span>
    </div>
    <el-form :label-position="labelPosition" label-width="80px">
      <el-form-item label="名称" class="change-label-calss">
        <el-input placeholder="请输入账号" v-model="account" clearable prefix-icon="el-icon-user"></el-input>
      </el-form-item>
      <el-form-item label="活动区域" class="change-label-calss">
        <el-input placeholder="请输入密码" v-model="password" show-password prefix-icon="el-icon-lock"></el-input>
      </el-form-item>
    </el-form>
    <el-button type="primary" round @click="login">登录</el-button>
  </div>
</template>
<script>
export default {
  name: 'Login',
  data () {
    return {
      account: '',
      password: '',
      img3: '../assets/logo.png',
      labelPosition: 'top'
    }
  },
  methods: {
    login () {
      if (this.account === 'admin' && this.password === '123456') {
        this.$router.push('Home')
      } else {
        this.$message.error('用户名或密码错误')
      }
    }
  }
}
</script>
<style lang="stylus" scoped>
.login
  width 25%
  margin 8% auto
  border-radius: 5px;
  padding: 2em 2em;
  background: #fff;
  border: 1px solid #eaeaea;
  box-shadow: 0 0 25px #cac6c6;

.change-label-calss /deep/ .el-form-item__label
  float: left!important;

.avatar
  vertical-align: middle;
  margin-bottom 2em

  img
    width: 1.1em;
    vertical-align: middle;
    margin-right: 0.5em;

  span
    vertical-align: middle;

.item
  margin-bottom 1em
  text-align left

  el-input
    margin-top 1em

</style>
