<script>
import axios from "axios";
import MainApp from './components/mainApp.vue';
import { store } from "./store"
import appLoaderVue from "./components/appLoader.vue";

export default {
  components: {
    MainApp,
    appLoaderVue

  },
  data() {
    return {
      store
    }
  },

  created() {

    axios.get("https://www.breakingbadapi.com/api/characters").then((resp) => {
      this.store.loading = true;
      this.store.characters = resp.data;
      console.log(this.store.characters);
      //qui resetto loading a false perchè i dati sono arrivati
      this.store.loading = false;
    })
  }

}
</script>

<template>
  <h1>Breaking Bad Api</h1>
  <appLoaderVue v-if="store.loading" />
  <MainApp v-else />
</template>

<style lang="scss">
@use "./styles/general.scss" as *;

h1 {
  color: white;
}
</style>
