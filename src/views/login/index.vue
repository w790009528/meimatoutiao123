<template>
  <div class="login">
      <el-card class="login-card">
        <div class="logo">
          <img src="../../assets/img/logo_index.png" alt="">
        </div>
        <!-- 表单组件 el-form表单容器 -->
        <el-form :model="loginForm" :rules="loginRules" style='margin-top:20px'>
           <!-- 表单项 -->
          <el-form-item prop="mobile">
            <!-- 放置组件内容 -->
            <!-- 绑定手机号 -->
            <el-input v-model="loginForm.mobile" placeholder="请输入手机号"></el-input>

          </el-form-item>
            <el-form-item prop="code">
              <el-input v-model="loginForm.code" style="width:280px" placeholder="请输入验证码"></el-input>
              <el-button style="float:right">发送验证码</el-button>
            </el-form-item>
            <el-form-item prop="check">
              <el-checkbox v-model="loginForm.check">我已阅读霸王条款和不平等条约</el-checkbox>
            </el-form-item>
            <el-form-item>
             <el-button type="primary" style="width:100%">登录</el-button>
            </el-form-item>
        </el-form>
      </el-card>
  </div>
</template>

<script>
export default {
  data () {
    return {
      loginForm: {
        mobile: '', // 手机号
        code: '', // 验证码
        check: false // 是否勾选协议
      },
      // 定义 rules
      loginRules: {
        mobile: [{
          required: true,
          message: '填了吗？'
        }, {
          pattern: /^1[3456789]\d{9}$/,
          message: '格式对吗？老弟。'
        }],
        code: [{
          required: true,
          message: '你填了吗?'
        }, {
          pattern: /^\d{6}$/,
          message: '验证码就6位数'
        }]
      }
    }
  }
}
</script>

<style lang='less' scoped>
  .login {
    background-image: url('../../assets/img/login_bg.jpg');
    height: 100vh;
    background-size: cover;
    display: flex;
    justify-content: center;
    align-items: center;
    .login-card {
      width: 440px;
      height: 350px;
      .logo {
        text-align: center;
        img {
          height: 40px;
        }
      }
    }
}
</style>
