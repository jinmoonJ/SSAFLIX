<template>
  <div @keyup.enter="login">
    <div class="authForm">
      
      <div class="loginInput">
        <h2>로그인</h2>
        <input class="form-control" id="username" v-model="credentials.username" type="text" placeholder="아이디">
        <input class="form-control" id="password" v-model="credentials.password" type="password" placeholder="비밀번호">
        <button @click="login" class="btn submitBtn">로그인</button>
      
      <div class="loginAddOn">
        <p style="cursor:pointer">도움이 필요하신가요?</p>
        <div>
          LETFLIX 회원이 아닌가요? <a :href="signupLink">지금 가입하세요.</a>
        </div>
      </div>
      </div>
      
    </div>
  </div>
</template>

<script>
export default {
  name: 'Login',
  data() {
    return {
      signupLink: '/accounts/signup/',
      credentials: {
        username: null,
        password: null,
      }
    }
  },
  methods: {
    login() {
      this.$store.dispatch('login', this.credentials)
    }
  }
}
</script>

<style>
  @import '../../assets/styles/common.css';
</style>
