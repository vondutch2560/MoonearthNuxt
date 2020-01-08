<template>
  <div class="index-page">
    <slide-home />
    <new-arrivals />
  </div>
</template>

<script>
import SlideHome from '~/components/SlideHome.vue'
import NewArrivals from '~/components/NewArrivals.vue'

export default {
  components: {
    SlideHome,
    NewArrivals
  }
}
</script>
