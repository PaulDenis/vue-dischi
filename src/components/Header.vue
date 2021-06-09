<template>
    <header>
        <img src="../assets/spotify.png" alt="Spotify logo">
    </header>
</template>

<script>
export default {
    name: 'Header'
}
</script>

<style lang="scss" scoped>

    header {
        position: fixed;
        top: 0;
        left: 0;
        height: 75px;
        width: 100%;
        background-color: #2e3a46;
        img {
            height: 55px;
            margin-top: 10px;
            margin-left: 25px;
        }
    }

</style>