<template>
   <div class="ms-col">
        <img :src="poster" :alt="author">
        <h2 class="text-white">{{title}}</h2>
        <div class="text-secondary">{{author}}</div>
        <div class="text-secondary">{{gender}}</div>
        <div class="text-secondary">{{year}}</div>
    </div>
</template>

<script>
export default {
    name:"DiscLibrary",
    props:{
        author: String,
        genre: String,
        poster: String,
        title: String,
        year: String,
    }
}
</script>

<style scoped lang="scss">
    .ms-col{
        width:calc(100% / 5 - 20px);
        margin: 10px;
        padding: 20px;
        text-align: center;
        background-color: #2e3a46;
        img{
            width: 150px;
            height: 150px;
            object-fit: cover;
        }
       
       
    }
</style>