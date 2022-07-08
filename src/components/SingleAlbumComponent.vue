<template>
    <div class="album">
        <div class="album-cover">
            <img :src="album.poster" :alt="album.genre">
        </div>
        <div class="album-text">
            <div class="album-title">
                <h2>{{album.title}}</h2>
            </div>
            <div class="album-info">
                <div class="album-author">
                    <span>{{album.author}}</span>
                </div>
                <div class="album-date">
                    <span>{{album.year}}</span>
                </div>
            </div>
        </div>
    </div>
</template>

<script>

export default {
    name: "SingleAlbumComponent",
    props: {
        album: Object,
    },
}
</script>

<style lang="scss" scoped>

// *STYLING
.album {
    padding: 0.8rem;
    width: calc((100% / 5) - 0.8rem);
    background-color: #2e3a46;

    .album-cover {
        aspect-ratio: 1/1;

        img {
            height: 100%;
            object-fit: cover;
        }
    }
}
.album-text {
    text-align: center;

    h2 {
        margin-block: 0.9rem;
        font-size: 1rem;
        text-transform: uppercase;
        color: #fff;
    }
    .album-author,
    .album-date {
        font-size: 0.7rem;
        color:#767870;
    }
}
</style>