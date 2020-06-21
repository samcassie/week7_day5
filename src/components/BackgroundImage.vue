<template lang="html">

    <img :src="images[5].download_url" alt="">

</template>

<script>



    export default {
        name: 'background-image',
        props: ['images']
    }

</script>

<style lang="css" scoped>

    img {
        position: absolute;
        left: 0px;
        top: 0px;
        height: 100%;
        width: 100%;
        z-index: -100;
    }

</style>
