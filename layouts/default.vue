<template>
  <div id="root">
    <Header />
    <SearchBar />
    <nuxt />
    <Map />
    <Footer />
  </div>
</template>

<script>
import Header from '~/components/layout/Header.vue'
import SearchBar from '~/components/layout/SearchBar.vue'
import Map from '~/components/layout/Map.vue'
import Footer from '~/components/layout/Footer.vue'

export default {
  components: {
    Header,
    SearchBar,
    Map,
    Footer
  }
}
</script>
