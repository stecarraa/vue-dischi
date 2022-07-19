<template>
<div class="container-fluid ms-bg">


<div class=" container loading-screen text-white" v-if=" loadingInProgress==true">
  <h1>Caricamento in corso.......</h1>

</div>


<div v-else >
<div class="container d-flex flex-wrap ">
        <DiscLibrary v-for="(album, index) in albums" :key="index"
            
            :author="album.author"
            :genre="album.genre"
            :poster="album.poster"
            :title="album.title"
            :year="album.year"
        />
</div>
</div>
    </div>

   

</template>

<script>
import axios from "axios";
import DiscLibrary from "./DiscLibrary.vue";


export default {

name:'MyMainContent',
    components: {
        DiscLibrary,
        
    },
    data: function() {
        return {
            albums: [],
            loadingInProgress: true,
        }
    },
    methods: {

              

        getAlbumsList: function() {
          this.loadingInProgress=true

             {
                axios.get("https://flynn.boolean.careers/exercises/api/array/music")
                    .then((result) => {
                        this.albums = result.data.response;
                                  this.loadingInProgress=false

                    }
                )
            }
        }
    },
 

    created() {
        this.getAlbumsList();
        
    },
}
</script>

<style lang="scss" scoped>
.ms-bg{
  background-color: #1E2D3B;
}

.loading-screen{
 img{
  height: 50%;
 }
}


</style>