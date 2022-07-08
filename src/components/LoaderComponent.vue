<template>
    <div class="loader flex">
        <span>
            <i class="fa-solid fa-spinner"></i>
        </span>
    </div>
</template>

<script>
export default {
    name: "LoaderComponent",
}
</script>

<style lang="scss" scoped>

// *STYLING
.loader {
    font-size: 4rem;
    color: #1dd55f;
    position: absolute;
    left: 50%;
    top: 60%;
    transform: translate(-50%, -50%);
    z-index: 1000;

    span {
        animation: loadingPulse 2s linear infinite;

        i {
            animation: loadingSpin 1.5s linear infinite;
        }
    }
}
@keyframes loadingSpin {
    from {
        transform: rotate(0deg);
    }
    to {
        transform: rotate(360deg);
    }
}
@keyframes loadingPulse {
    0% {
        transform: scale(1);
    }
    50% {
        transform: scale(1.2);
    }
    100% {
        transform: scale(1);
    }
}
</style>