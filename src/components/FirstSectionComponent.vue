<template>
    <section>
        <div class="container">
            <select name="genre-select" id="genre" @change="filterGenre()" v-model="filteredGenre">
                <option value="all" selected>All</option>
                <option value="rock">Rock</option>
                <option value="pop">Pop</option>
                <option value="jazz">Jazz</option>
                <option value="metal">Metal</option>
            </select>
            <div class="flex">
                <SingleAlbumComponent v-for="element in filterdArray" :key="element.id" :album="element"/>
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
            filteredGenre: "all",
            filteredAuthor: "all",
            albums: [],
            filteredArray: [],
        }
    },
    methods: {
        filterGenre() {
            if(this.filteredGenre !== "all") {
                this.filterdArray = this.albums.filter((element) => {
                    return element.genre.toLowerCase() === this.filteredGenre;
                });
            } else {
                this.filterdArray = this.albums;
            }

            // !DEBUG
            // console.log(this.filterdArray);
        },
    },
    mounted() {
        setTimeout(() => {
            axios.get("https://flynn.boolean.careers/exercises/api/array/music")
            .then((response) => {
                this.albums = response.data.response;
                this.filterdArray = response.data.response;
            });
        }, 500);
    }
}
</script>

<style lang="scss" scoped>
// *STYLING
section {
    padding-block: 3rem;

    .container {
        text-align: center;
        
        > .flex {
            flex-wrap: wrap;
            gap: 1rem;
        }
    }
}
#genre {
    margin-block: 1rem;
    border: 1px solid #1dd55f;
    border-radius: 0.15rem;
    background-color: #2e3a46;
    color: #fff;
}
</style>