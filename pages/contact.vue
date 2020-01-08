<template>
  <div class="contact-page">
    <div class="row">
      <banner-page :title="'Liên Hệ Với Chúng Tôi'" />
      <breadcrumb :breadcrumb="propsBreadcrumb" />
    </div>
  </div>
</template>

<script>
import BannerPage from '~/components/BannerPage.vue'
import Breadcrumb from '~/components/Breadcrumb.vue'

export default {
  transition: 'default',
  components: {
    BannerPage,
    Breadcrumb
  },

  data() {
    return {
      propsBreadcrumb: [
        {
          name: 'Liên hệ',
          link: '/contact'
        }
      ]
    }
  }
}
</script>
