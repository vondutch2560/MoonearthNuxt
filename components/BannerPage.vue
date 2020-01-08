<template>
  <div class="bg-title-page">
    <h2>{{ title }}</h2>
  </div>
</template>

<script>
export default {
  props: {
    title: {
      type: String,
      default: 'Moon & Earth'
    }
  }
}
</script>

<style>
.bg-title-page {
  position: relative;
  margin-top: 35px;
  padding-bottom: 230px;
  background: url('~assets/images/bg-title-page.jpg') no-repeat;
  background-size: cover;
  background-position: center center;
}
.bg-title-page:after {
  content: '';
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  background-color: rgba(255, 255, 255, 0.3);
}
.bg-title-page h2 {
  display: inline-block;
  position: absolute;
  z-index: 1;
  right: 0;
  left: 0;
  top: 50%;
  transform: translateY(-50%);
  text-align: center;
  margin: auto;
  font-size: 40px;
  font-family: 'Playfair Display';
  font-weight: 400;
}
</style>
