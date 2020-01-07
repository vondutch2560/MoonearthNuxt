<template>
  <div id="root">
    <Header />
    <nuxt />
    <Map />
    <Footer />
  </div>
</template>

<script>
import Header from '~/components/layout/Header.vue'
import Map from '~/components/layout/Map.vue'
import Footer from '~/components/layout/Footer.vue'

export default {
  components: {
    Header,
    Map,
    Footer
  }
}
</script>
