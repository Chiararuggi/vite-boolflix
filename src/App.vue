<script>
import axios from "axios";
import { store } from "./store";
import AppHeader from "./components/AppHeader.vue";
export default {
  components: {
    AppHeader,
  },

  data() {
    return {
      store,
    };
  },
  mounted() {},
  methods: {},
};
</script>

<template>
    <AppHeader />
</template>

<style scoped></style>
