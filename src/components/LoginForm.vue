<template>
    <q-form class="loginForm sign-in-form q-pa-md  q-gutter-md" style="max-width: 400px"
      @submit="onSubmit"

    >
      <q-input
        label="邮箱/手机"
        lazy-rules
        v-model="loginUser.email"
        :rules="[val => (val && val.length > 0) || '必填项不能为空']"
        clearable
      />

      <q-input
        label="密码"
        lazy-rules
        type="password"
        v-model="loginUser.password"
        :rules="[val => (val !== null && val !== '') || '必填项不能为空']"
        clearable
      />

      <div>
          <q-btn label="点击完成验证" color="primary" @click="valiCode" class="full-width"/>
        <q-btn label="提交" type="submit" color="primary" class="full-width q-mt-md" :disable="successValiCode"/>

      </div>
          <!-- 找回密码 -->
    <div class="tiparea">
      <p>忘记密码？ <a>立即找回</a></p>
    </div>
    </q-form>
</template>
<script>
export default {
  data () {
    return {
      successValiCode: true,
      loginUser: {
        email: '',
        password: ''
      }
    }
  },
  methods: {
    onSubmit () {
      if (this.loginUser.email !== '' && this.loginUser.password !== '') {
        this.$q.notify({
          color: 'green-4',
          textColor: 'white',
          icon: 'cloud_done',
          message: '提交成功'
        })
      } else {
        this.$q.notify({
          color: 'red-5',
          textColor: 'white',
          icon: 'warning',
          message: '登录失败'
        })
      }
    },
    onReset () {
      this.loginUser.email = ''
      this.loginUser.password = ''
    },
    valiCode () {
      this.successValiCode = false
    }
  }
}
</script>
<style scoped>
/* form */
.loginForm {
  margin-top: 20px;
  background-color: #fff;
  padding: 20px 40px 20px 20px;
  border-radius: 5px;
  box-shadow: 0px 5px 10px #cccc;
}
.tiparea {
  text-align: right;
  font-size: 12px;
  color: #333;
}
.tiparea p a {
  color: #409eff;
}
</style>
