<template lang="html">

    <div id="selector">
        <label for="">Select the image to view:   </label>
        <select v-model="selectedImage" v-on:change="handleChange">
            <option v-for="(image, index) in images" :image="image" :key="index" :value="image">{{index}}</option>
        </select>
    </div>


</template>

<script>

    import { eventBus } from '../main.js'

    export default {
        name: "selector",
        data(){
            return {
                selectedImage: null
            }
        },
        props: ['images'],
        methods: {
            handleChange(){
                eventBus.$emit('image-selected', this.selectedImage)
            }
        }
    }

</script>

<style lang="css" scoped>

    #selector {
        padding: 10px;
        padding-bottom: 30px;

    }

    button {
        padding: 10px;
        margin: 5px;
    }

    label {
        font-size: 20px;
        margin-left: 20px;
    }
</style>
