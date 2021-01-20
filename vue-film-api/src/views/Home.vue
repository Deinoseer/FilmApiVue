<template>
  <div class="bar">
    <search />
    <preloader />
    <div>
      <div v-for="(movie, index) in movieslist.data" :key="index">
        <FilmList
          :title="movie.title"
          :year="movie.year"
          :genres="movie.genres"
          :poster="movie.poster"
          :directors="movie.directors"
          :actors="movie.actors"
          :description="movie.description"
          @showMovie="showMovie(movie.id)"
        />
      </div>
    </div>
  </div>
</template>

<script>
import FilmList from "../components/FilmsList";
import axios from "axios";
import Preloader from "@/components/Preloader.vue";
import Search from "../components/Search.vue";

export default {
  components: { FilmList, Search, Preloader },
  name: "Home",
  data() {
    return {
      show: true,
      movieslist: [],
    };
  },
  mounted() {
    axios
      .get("https://floating-sierra-20135.herokuapp.com/api/movies")
      .then((response) => (this.movieslist = response.data));
  },
  methods: {
    showMovie(index) {
      console.log(index);
    },
  },
};
</script>
<style lang="scss">
.bar {
  width: 1400px;
  margin: 0 auto;
}
</style>
