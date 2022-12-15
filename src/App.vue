<script >
import axios from "axios";
import AppHeader from './components/AppHeader.vue'
import CharacterList from './components/CharacterList.vue'
import Select from './components/select.vue';


import { store } from './store.js'

export default {

  name: "App",
  components: {
    AppHeader,
    CharacterList,
    Select
  },
  data() {
    return {
      store,
    }
  },
  methods: {
    getCharacters() {
      let myUrl = store.apiURL;
      store.status = store.status;

      if (store.status === "Alive") {

        myUrl += `?${store.parameter}=${store.status}`

      } else if (store.status === "Dead") {

        myUrl += `?${store.parameter}=${store.status}`

      } else if (store.status === "unknown") {

        myUrl += `?${store.parameter}=${store.status}`

      }

      axios
        .get(myUrl)
        .then(res => {
          store.characterList = res.data.results
        })
        .catch(err => {
          console.log("Errori", err);
        }

        );
    }
  },
  mounted() {
    this.getCharacters();
  }
}

</script>


<template>

  <AppHeader :msg="store.titolo" />

  <main>
    <Select @filterCharacter="getCharacters" />
    <CharacterList />
  </main>

</template>

<style lang="scss">
@use "../src/styles/generals.scss";


main {
  padding-top: 20px;
}
</style>
