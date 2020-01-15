<template>
  <div class="contact-page">
    <div class="row">
      <banner-page :title="'Liên Hệ Với Chúng Tôi'" />
      <breadcrumb :breadcrumb="propsBreadcrumb" />
      <div class="main-contact grid">
        <div class="contact-map">
          <iframe
            src="https://www.google.com/maps/embed?pb=!1m18!1m12!1m3!1d3919.334704692508!2d106.665411414621!3d10.78565656197296!2m3!1f0!2f0!3f0!3m2!1i1024!2i768!4f13.1!3m3!1m2!1s0x31752f25a69f1625%3A0x862d585d7a216ec6!2sMoon%26Earth%20Home%20Decor!5e0!3m2!1svi!2s!4v1568095524539!5m2!1svi!2s"
            width="575"
            height="500"
            frameborder="0"
            style="border:0"
            allowfullscreen=""
          ></iframe>
        </div>
        <div class="contact-form">
          <h3>Get in touch</h3>
          <p></p>
          <form
            id="form-collect-info-customer"
            method="POST"
            autocomplete="off"
          >
            <label for="name-customer">YOUR NAME *</label
            ><input
              id="name-customer"
              class="input-default"
              type="text"
              name="name"
            /><label for="email-customer">EMAIL *</label
            ><input
              id="email-customer"
              class="input-default"
              type="text"
              name="email"
            /><label for="message-customer">YOUR MESSAGE</label
            ><textarea
              id="message-customer"
              class="textarea-default"
              name="message"
            ></textarea
            ><a href="javascript:;" class="btn btn-send">Send Us</a>
          </form>
        </div>
      </div>
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

  asyncData() {
    return new Promise((resolve) => {
      // eslint-disable-next-line nuxt/no-timing-in-fetch-data
      setTimeout(function() {
        resolve({
          propsBreadcrumb: [
            {
              name: 'Liên hệ',
              link: '/contact'
            }
          ]
        })
      }, 10)
    })
  }
}
</script>
