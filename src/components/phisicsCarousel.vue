<template>
  <div class="q-pa-md">
    <q-carousel
      arrows
      animated
      autoplay="100"
      infinite
      v-model="slide"
      height="500px"
    >
      <q-carousel-slide name="first" img-src="../assets/mechanics.jpg">
        <div class="absolute-bottom custom-caption">
          <div class="text-h2">Механика</div>
          <div class="text-subtitle1">Механика</div>
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="second" img-src="../assets/thermodinamics.jpg">
        <div class="absolute-bottom custom-caption">
          <div class="text-h2">Термодинамика</div>
          <div class="text-subtitle1">Термодинамика</div>
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="optics" img-src="../assets/prism.jpg">
        <div class="absolute-bottom custom-caption">
          <div class="text-h2">Оптика</div>
          <div class="text-subtitle1">Оптика</div>
        </div>
      </q-carousel-slide>
      <q-carousel-slide name="electro" img-src="../assets/electro.jpg">
        <div class="absolute-bottom custom-caption">
          <div class="text-h2">Электродинамика</div>
          <div class="text-subtitle1">Электродинамика </div>
        </div>
      </q-carousel-slide>
    </q-carousel>
  </div>
</template>

<script>
import { ref } from 'vue'

export default {
   name: "phisicsCarousel",

  setup () {
    return {
      slide: ref('first')
    }
  }
}
</script>

<style lang="sass" scoped>
.custom-caption
  text-align: center
  padding: 12px
  color: white
  background-color: rgba(0, 0, 0, .3)
</style>
