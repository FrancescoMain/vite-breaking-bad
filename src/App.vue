<script >
import axios from "axios";
import AppHeader from './components/AppHeader.vue'
import CharacterList from './components/CharacterList.vue'


import { store } from './store.js'

export default {

  name: "App",
  components: {
    AppHeader,
    CharacterList
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCharacters() {
      axios
        .get(store.apiURL)
        .then(res => {
          store.characterList = res.data.results
        })
        .catch(err => {
          console.log("Errori", err);
        }

        );
    }
  }
}

</script>


<template>
  <AppHeader :msg="store.titolo" />
  <main>
    <CharacterList />
  </main>

</template>

<style lang="scss">
@use "../src/styles/generals.scss";


main {
  padding-top: 20px;
}
</style>
