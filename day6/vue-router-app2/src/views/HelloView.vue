<template>
  <div>
    <h1>Hello</h1>
    <h1>{{user.name || '안녕'}}</h1>
    <h1>{{user.email || '자료없다'}}</h1>
    <button @click="back2">뒤로 2칸</button>
    <button @click="replacePage">REPLACE</button>
  </div>
</template>

<script>
export default {
    name: 'HelloView',
    data() {
        return {
            user: this.$route.params.user,
        }
    },
    methods: {
        back2() {
            this.$router.go(-2)
        },
        replacePage() {
            this.$router.replace({name: 'about'})
        }
    }
}
</script>

<style>

</style>