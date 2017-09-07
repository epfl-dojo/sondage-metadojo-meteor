<template>
    <div>
        <vue-slider ref="slider"
                    v-model="value"
                    :data="opt"
                    :piecewise="true"
                    :piecewiseLabel="true"
                    :piecewiseStyle="piecewiseStyle"
                    :piecewiseActiveStyle="piecewiseActiveStyle"
                    :labelActiveStyle="labelActiveStyle"
        ></vue-slider>
    </div>
</template>
<script>
    let vueSlider;
    if (Meteor.isClient) {
        vueSlider = require('/src/imports/ui/vue2-slider-forked.vue').default;
    }

    export default {
        components: {
            vueSlider
        },
        data () {
          return {
              value: "neutre",
              opt: ["pas content", "bof", "neutre", "trop bien!"],

              piecewiseStyle: {
                  "backgroundColor": "#ccc",
                  "visibility": "visible",
                  "width": "12px",
                  "height": "12px"
              },
              piecewiseActiveStyle: {
                  "backgroundColor": "#3498db"
              },
              labelActiveStyle: {
                  "color": "#3498db"
              }
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
