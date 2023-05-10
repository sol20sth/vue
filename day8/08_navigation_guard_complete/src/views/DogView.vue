<template>
  <div>
    <h1>DogView</h1>
    <p v-if="!imgSrc">{{ message }}</p>
    <img :src="imgSrc" alt="" v-if="imgSrc">
    <br>

  </div>
</template>

<script>
import axios from 'axios'
export default {
    name: 'DogView',
    data() {
        return {
            imgSrc: null,
            message: '로딩중......'
        }
    },
    methods: {
        getDogImage() {
            const breed = this.$route.params.breed
            const dogImageSearchUrl = `https://dog.ceo/api/breed/${breed}/images/random`
            
            axios({
                method: 'get',
                url: dogImageSearchUrl
            })
            .then((response) => {
                const dogImgSrc = response.data.message
                this.imgSrc = dogImgSrc
                
            })
            .catch((error) => {
                this.message=`${this.$route.params.breed}는 없는 품종입니다`
                console.log(error)
                this.$router.push('/404')
            })
        }
    },
    created(){
        this.getDogImage()
    }
}
</script>

<style>

</style>