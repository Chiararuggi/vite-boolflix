<script>
import { store } from "../store.js"

export default {
    name: "AppSearch",
    //emits: ["search"],
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
    <div>
        <input type="text" placeholder="Movie name" v-model="store.userInput">
        <button @click="search">Find</button>
    </div>
</template>


<style scoped>
</style>