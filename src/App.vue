<script>
import axios from "axios";
import MainApp from './components/mainApp.vue';
import { store } from "./store"

export default {
  components: {
    MainApp,

  },
  data() {
    return {
      store
    }
  },

  created() {
    axios.get("https://www.breakingbadapi.com/api/characters").then((resp) => {
      this.store.characters = resp.data;
      console.log(this.store.characters);
    })
  }

}
</script>

<template>
  <h1>Breaking Bad Api</h1>
  <MainApp />
</template>

<style lang="scss">
@use "./styles/general.scss" as *;

h1 {
  color: white;
}
</style>
