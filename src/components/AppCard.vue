<script>
export default {
  name: "AppCard",
  props: {
    info: Object,
  },
};
</script>

<template>
  <div class="card">
    <p>{{ info.title }}</p>
    <p>{{ info.original_title }}</p>
    <p>{{ info.vote_count }}</p>
    <p>{{ info.original_language }}</p>
    <img :src="`https://image.tmdb.org/t/p/w342/${info.poster_path}`" />
  </div>
</template>

<style scoped>
.card {
  color: black;
}
</style>
