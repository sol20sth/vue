<template>
  <div class="secondAbout">
    <h1>This is an second page</h1>
    <h2>신기방기</h2>
    <button @click="routerChange">홈으로 이동방법1</button>
    <router-link :to="{ name : 'home'}"> Home 이동방법2</router-link>
  </div>
</template>

<script>

export default {
  name: 'secondAbout',
  methods: {
    routerChange() {
      this.$router.push({name: 'home'})
    }
  }
}
</script>



