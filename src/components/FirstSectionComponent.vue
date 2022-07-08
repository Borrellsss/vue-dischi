<template>
    <section>
        <div class="container">
            <div class="flex">
                <SingleAlbumComponent v-for="element in albums" :key="element.id" :album="element"/>
            </div>
            <LoaderComponent v-if="albums.length < 10"/>
        </div>
    </section>
</template>

<script>
import axios from "axios";
import SingleAlbumComponent from "./SingleAlbumComponent.vue";
import LoaderComponent from "./LoaderComponent.vue";

export default {
    name: "FirstSectionComponent",
    components: {
        SingleAlbumComponent,
        LoaderComponent,
    },
    data() {
        return {
            albums: [],
        }
    },
    mounted() {
        setTimeout(() => {
            axios.get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((response) => {
                this.albums = response.data.response;
            });
        }, 4000)
    }
}
</script>

<style lang="scss" scoped>
// *STYLING
section {
    padding-block: 3rem;

    .container {
        
        > .flex {
            flex-wrap: wrap;
            gap: 1rem;
        }
    }
}
</style>