<template>
  <div class="login-page">
    <div class="logo-area"></div>
    <input class="username-input" type="text" placeholder="用户名" v-model="username">
    <input class="pass-input" type="password" placeholder="密码" v-model="password">
    <div class="validation-tips">6-20位字符，区分大小写</div>
    <div class="login-btn" @click="login">登录</div>
  </div>
</template>

<script>
  import { Toast } from 'mint-ui'
//  import AccountService from '../assets/js/fetch_service/account.js'
  export default{
    data () {
      let username
      let password
      return {
        username: username,
        password: password
      }
    },
    methods: {
      login () {
//        let self = this
//        AccountService.login(self.username, self.password, function (data) {
//          if (data.status === 0) {
//            localStorage.setItem('access_token', data.data.access_token)
//            Toast({
//              message: '登录成功',
//              iconClass: 'icon icon-success',
//              duration: 2000
//            })
//          } else {
//            Toast({
//              message: data.msg,
//              iconClass: 'icon icon-error',
//              duration: 2000
//            })
//            return
//          }
//          window.location.href = '/#/risk-msg-list'
//        })
        let data = {
          status: 0,
          msg: 'login success',
          data: {
            access_token: 'ssdsdsdsdsdss'
          }
        }
        if (data.status === 0) {
          localStorage.setItem('access_token', data.data.access_token)
          Toast({
            message: '登录成功',
            iconClass: 'icon icon-success',
            duration: 2000
          })
        } else {
          Toast({
            message: data.msg,
            iconClass: 'icon icon-error',
            duration: 2000
          })
          return
        }
        window.location.href = '/#/nav-1-list'
      }
    }
  }
</script>

<style scoped lang="scss" rel="stylesheet/scss">
  @import "../assets/css/var.scss";
  @import "../assets/css/login.scss";
</style>
