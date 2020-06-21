<template>
  <div>
    <h1>Photography viewer</h1>
    <background-image :images='images' > </background-image>
    <selector :images='images'></selector>
    <image-details :image='selectedImage'></image-details>

  </div>
</template>

<script>

    import { eventBus } from './main.js'

    import ImageDetails from './components/ImageDetails.vue';
    import BackgroundImage from './components/BackgroundImage.vue';
    import Selector from './components/Selector.vue';

    export default {

        name: 'app',
        data(){
            return {
                images: [],
                selectedImage: null
            };
        },
        mounted(){
            fetch('https://picsum.photos/v2/list')
            .then(res => res.json())
            .then(images => this.images = images)


            eventBus.$on('image-selected', (selectedImage) => {
                (this.selectedImage = selectedImage)
            })
        },
        components: {
            "background-image": BackgroundImage,
            "selector": Selector,
            "image-details": ImageDetails,

        }
    }

</script>

<style>

    html {
        margin: 0;
        padding: 0;
    }

    h1 {
        z-index: 100;
        color: white;
        text-shadow: -1px -1px 0 #000, 1px -1px 0 #000, -1px 1px 0 #000, 1px 1px 0 #000;
        padding: 10px;
        border: 2px solid white;
        width: 60%;
    }

    backgroundImage {
        z-index: -100;
    }
</style>
