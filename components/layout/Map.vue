<template>
  <div class="map">
    <div class="navigation-map">
      <div class="see-map item-map">
        <a @click="toogleMap">SEE MAP</a>
      </div>
      <div class="scroll-up item-map">
        <a @click="scrollUp">SCROLL UP</a>
      </div>
    </div>
    <div ref="googlemap" class="row google-map"></div>
  </div>
</template>
<script>
export default {
  mounted() {
    this.$refs.googlemap.innerHTML = `<iframe
        src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3919.334704692508!2d106.665411414621!3d10.78565656197296!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x31752f25a69f1625%3A0x862d585d7a216ec6!2sMoon%26Earth%20Home%20Decor!5e0!3m2!1svi!2s!4v1568095524539!5m2!1svi!2s"
        width="${this.$refs.googlemap.offsetWidth}"
        height="460"
        frameborder="0"
        style="border:0"
        allowfullscreen=""
      ></iframe>`
  },
  methods: {
    toogleMap() {
      this.$refs.googlemap.classList.toggle('show-map')
      this.$scrollToSmooth('.see-map', null, -30)
    },
    scrollUp() {
      this.$scrollToSmooth('top')
    }
  }
}
</script>
