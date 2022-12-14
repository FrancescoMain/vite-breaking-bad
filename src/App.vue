<script >
import AppHeader from './components/AppHeader.vue'


import { store } from './store.js'

export default {

  name: "App",
  components: {
    AppHeader
  },
  data() {
    return {
      store,
    }
  }
}

</script>


<template>
  <AppHeader :msg="store.titolo" />
</template>

<style lang="scss">
@use "../src/styles/generals.scss";


main {
  padding-top: 20px;
}
</style>
