<script>
import axios from "axios";
import { store } from "./store.js";
import AppSearch from "./components/AppSearch.vue";
import AppCard from "./components/AppCard.vue";

export default {
  components: {
    AppSearch,
    AppCard,
  },

  data() {
    return {
      store,
    };
  },
  mounted() {
    this.getMovies();
  },
  methods: {
    getMovies() {
      let request = {
        method: "GET",
        url: this.store.apiUrl,
        params: {
          query: this.store.userInput,
          include_adult: "false",
          language: "it-IT",
          page: "1",
          api_key: "a40e8b72e402747e25bffe3a5b0ed437",
        },
        headers: {
          accept: "application/json",
        },
      };

      axios.request(request).then((result) => {
        this.store.movieList = result.data.results;
      });
    },
  },
};
</script>

<template>
  <AppSearch @search="getMovies()" />
  <AppCard v-for="movie in store.movieList" :info="movie" />
  <p v-if="store.movieList.length == 0">No movies found</p>
</template>

<style scoped></style>
