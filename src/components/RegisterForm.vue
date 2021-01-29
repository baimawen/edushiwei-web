<template>

 <q-form  class="registerForm sign-up-form q-pa-md q-gutter-md" style="max-width: 400px">
        <q-input label="手机/邮箱" clearable/>
        <q-input label="密码(字母数字特殊字符6-16位)" clearable/>
            <q-toolbar>
                <q-input label="验证码" clearable />
            <q-btn class="q-ml-xl" size="md"  :loading="loadingCode" @click="sendCode" >发送验证码
                <template v-slot:loading>
        <q-spinner-gears class="on-left" /> {{time}}
      </template>
            </q-btn>
            </q-toolbar>
              <div>
        <q-btn label="提交" type="submit" color="primary" />
        <q-btn label="重置" type="reset" color="primary" flat />
      </div>
    </q-form>
</template>
<script>
export default {
  data () {
    return {
      loadingCode: false,
      time: 0
    }
  },
  methods: {
    sendCode () {
      this.loadingCode = true
      this.time = 60
      this.timer()
    },
    timer () {
      if (this.time <= 0) {
        this.loadingCode = false
      } else {
        this.time--
        setTimeout(this.timer, 1000)
      }
    }
  }
}
</script>
<style scoped>

</style>
