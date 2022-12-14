<script >
import SingleCharacter from '../components/SingleCharacter.vue'

import { store } from "../store.js";

export default {

    name: "CharacterList",
    components: {
        SingleCharacter
    },
    data() {
        return {
            store,
        }
    }

}
</script>

<template>

    <section class="container">
        <div class="row">
            <SingleCharacter />
        </div>
    </section>


</template>

<style lang="scss" scoped>

</style>
