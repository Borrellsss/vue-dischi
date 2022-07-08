<template>
    <header>
        <div class="flex">
            <div class="header-logo">
                <img src="https://pnggrid.com/wp-content/uploads/2021/05/Spotify-PNG-Logo-768x767.png" alt="Spotify Logo">
            </div>
        </div>
    </header>
</template>

<script>
export default {
    name: "HeaderComponent",
}
</script>

<style lang="scss" scoped>

// *STYLING
header {
    padding: 0.7rem 1rem;
    background-color: #2e3a46;

    .header-logo {
        width: 2rem;
    }
}
</style>