<script >
import { store } from "../store.js";

export default {

    name: "CharacterList",
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
            <div class="character text-center">
                <img src="https://rickandmortyapi.com/api/character/avatar/1.jpeg" alt="">
                <h4>nome</h4>
                <div>stato</div>
                <div class="font-weight-bold">specie</div>
            </div>
        </div>
    </section>


</template>

<style lang="scss" scoped>
h4 {
    text-transform: capitalize;

    &::after {
        content: '';
        display: block;
        width: 40px;
        height: 1px;
        margin: 1rem, auto;
    }
}

img {
    border-radius: 50%;
    box-shadow: 0 0 6px 3px rgba(#000, 0.15);
}
</style>
