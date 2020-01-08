<template>
  <div class="index-page">
    <slide-home />
    <new-arrivals />
    <slogan />
    <about-us />
  </div>
</template>

<script>
import SlideHome from '~/components/SlideHome.vue'
import NewArrivals from '~/components/NewArrivals.vue'
import Slogan from '~/components/Slogan.vue'
import AboutUs from '~/components/AboutUs.vue'

export default {
  components: {
    SlideHome,
    NewArrivals,
    Slogan,
    AboutUs
  },

  transition: 'default'
}
</script>
