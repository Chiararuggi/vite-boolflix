<script>
export default {
  name: "AppCard",
  props: {
    info: Object,
  },

  methods: {},
};
</script>

<template>
    <div class="card">
      <p>Titolo: {{ info.title }}</p>
      <p>Titolo originale: {{ info.original_title }}</p>
      <p>Voto: {{ info.vote_count }}</p>
      <p>Lingua originale:</p>
      <img
        v-if="info.original_language != null"
        :src="`/${info.original_language}.png`"
      />
      <img v-else src="/notFound.png" />
      <img
        v-if="info.poster_path != null"
        :src="`https://image.tmdb.org/t/p/w342/${info.poster_path}`"
      />
      <img v-else src="/notFound.png" />
    </div>
</template>

<style scoped>
.card {
  color: black;
  width: fit-content;
  padding: 1rem;
}
</style>
