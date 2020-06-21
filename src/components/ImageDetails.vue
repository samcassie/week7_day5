<template lang="html">

    <div id="imageDetails" class="">
        <div>
            <h3 id="author">Author: {{image.author}}</h3>
            <h4>Original dimensions: {{image.width}} by {{image.height}}</h4>
            <h4>URL: <span id="link">{{image.url}}</span></h4>
        </div>
        <img id="imagePic" :src="image.download_url" alt="">
    </div>

</template>

<script>

    export default {
        name: 'image-details',
        props: ['image']

    }

</script>

<style lang="css" scoped>

    #imageDetails {
        border: 2px solid white;
        padding: 10px;
        width: auto;
        max-width: 60%;
        display: flex;
        justify-content: space-between;

    }

    #author {
        color: white;
        text-shadow: -1px -1px 0 #000, 1px -1px 0 #000, -1px 1px 0 #000, 1px 1px 0 #000;
    }

    h3  {
        color: black;
        padding: 0p
    }

    #link {
        text-decoration: underline;
        color: blue;
    }

    #imagePic {
        width: auto;
        height: 200px;
    }
</style>
