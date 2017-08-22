<template>
    <div>
        <vue-slider ref="slider" v-model="value"></vue-slider>
    </div>
</template>
<script>
    let vueSlider;
    if (Meteor.isClient) {
        vueSlider = require('vue-slider-component')
    }

    export default {
        components: {
            vueSlider
        },
        data () {
          return {
            value: 1
          }
        }
    }
</script>

<style>
    /* The animation code */
    @keyframes example {
        from {background-color: red;}
        to {background-color: yellow;}
    }
    p {
        color: red;
        background-color: lightgray;
        animation-name: example;
        animation-duration: 4s;
    }
</style>
