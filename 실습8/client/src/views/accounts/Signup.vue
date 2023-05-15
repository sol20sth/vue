<template>
  <div>
    <form @submit.prevent="signup">
      <span>아이디를 입력하시오:</span><input type="text" v-model="username"><br>
      <span>비밀번호를 입력하시오:</span><input type="text" v-model="password1"><br>
      <span>비밀번호 재확인</span><input type="text" v-model="password2">
      <button type="submit" @click='signup'>만들기</button>
    </form>
  </div>
</template>

<script>
import axios from 'axios'
// import axios from 'axios'

export default {
  name: 'Singup',
  data: function () {
    return {
      username: '',
      password1: '',
      password2: '',
      idList: [],
    }
  },
  methods: {
    signup: function () {
      axios({
        method: 'POST',
        url: `http://127.0.0.1:8000/accounts/signup/`,
        data: {'username': this.username, 'password1': this.password1, 'password2': this.password2}
      })
      .then((res) => {
        console.log(res)
        // this.idList.push(res.data.user)
        // console.log(this.idList)
        // this.$router.push({name: 'Login'})
      })
      .catch((err) => {
        console.log(err)
        // alert('잘못된 아이디or비밀번호입니다.')
      })
    }
  }
}
</script>
