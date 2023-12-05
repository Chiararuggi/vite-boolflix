<script>
import { store } from "../store.js"

export default {
    name: "AppSearch",
    data() {
        return {
            store,
        }
    },
    methods: {
        search() {
            this.$emit("search");
        }
    },
    mounted() {
    }
}
</script>

<template>
    <input type="text" placeholder="Movie name" v-model="store.userInput">
    <button @click="search">Find</button>
</template>


<style scoped>
</style>