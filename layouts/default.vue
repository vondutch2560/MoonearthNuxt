<template>
  <div id="root">
    <Header />
    <nuxt />
  </div>
</template>

<script>
import Header from '~/components/layout/Header.vue'

export default {
  components: {
    Header
  }
}
</script>
