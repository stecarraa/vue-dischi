<template>
  <div class="container-fluid ms-bg">
    <div class="loading-screen" v-if="loadingInProgress == true">
      <h1>Caricamento in corso .....</h1>
      <div class="container">
        <img
          src="https://img.freepik.com/premium-vector/loading-bar-doodle-element-hand-drawn-line-sketch-style-slow-download-speed-progress-status-internet-load-bar-concept-isolated-vector-illustration_253081-853.jpg?w=2000"
          alt=""
        />
      </div>
    </div>
    <div v-else>
      <div>
        <select
          v-model="selectedGenre"
          @change="$emit('genreSelected', selectedGenre)"
        >
          <option value="">Seleziona un genere</option>
          <option
            v-for="(genre, index) in genresList"
            :value="genre"
            :key="index"
          >
            {{ genre }}
          </option>
        </select>
      </div>
      <div class="container d-flex flex-wrap">
        <DiscLibrary
          v-for="(album, index) in albums"
          :key="index"
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
  name: "MyMainContent",
 
  components: {
    DiscLibrary,
  },
  data: function () {
    return {
      albums: [],
      genresList:[],
      selectedGenre: "",
      loadingInProgress: true,
    };
  },
  methods: {
    getAlbumsList: function () {
      this.loadingInProgress = true;

      {
        axios
          .get("https://flynn.boolean.careers/exercises/api/array/music")
          .then((result) => {
            this.albums = result.data.response;
            this.loadingInProgress = false;
          });
      }
    },

setGenres(genreSelected){
      this.genresList=genreSelected;
    },
    setSelectedGenre(selectedGenreEvt){
      this.selectedGenre=selectedGenreEvt;
      
    }

  },

  created() {
    this.getAlbumsList();
  },
};
</script>

<style lang="scss" scoped>
.ms-bg {
  background-color: #1e2d3b;
}

.loading-screen {
  img {
    width: 100%;
    object-fit: cover;
    padding: 50px;
  }
}
</style>
