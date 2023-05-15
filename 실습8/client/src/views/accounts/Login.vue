<template>
  <div>
    <form @submit.prevent="login">
      <span>아이디 : </span><input type="text" v-model="loginId"><br>
      <span>비밀번호 : </span><input type="text" v-model="loginPassword">
      <button type="submit">로그인</button>
    </form>
  </div>
</template>

<script>
// import axios from 'axios'

export default {
  name: 'Login',
  data: function () {
    return {
      allIdList: this.idList ,
      loginId: '',
      loginPassword: '',
    }
  },
  methods: {
    login: function () {
      console.log(this.loginId)
      console.log(this.loginPassword)
      console.log(this.allIdList)
    },
    idList() {
      return this.params.idList
    }
  }
}
</script>
