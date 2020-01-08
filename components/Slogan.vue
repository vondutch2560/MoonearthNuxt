<template>
  <div class="row slogan grid">
    <div class="text-content">
      <div class="bg-text-content"></div>
      <h2>Where LOVE begins And never ends...</h2>
    </div>
    <div class="img-slogan">
      <div class="bg-slogan"></div>
    </div>
  </div>
</template>

<script>
export default {}
</script>

<style>
.row.slogan {
  grid-template-columns: 1fr 2fr;
  grid-gap: 35px;
  padding: 10px 0 80px 0;
}

.row.slogan .text-content {
  position: relative;
}
.row.slogan .text-content .bg-text-content {
  width: 100%;
  height: 270px;
  position: relative;
  text-align: center;
  border: 3px solid #eee;
  background: url('~assets/images/bg-slogan-text.jpg') no-repeat;
  background-size: 100%;
}
.row.slogan .text-content h2 {
  padding: 0 40px;
  margin: 0;
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  font-family: 'Playfair Display';
  font-weight: 400;
  text-align: center;
}

.row.slogan .img-slogan {
  position: relative;
}

.img-slogan .bg-slogan {
  position: absolute;
  top: 0;
  left: 0;
  right: 15px;
  bottom: 15px;
  transition: background-size 0.3s;
  background: url('~assets/images/bg-slogan-img.jpg') no-repeat;
  background-size: 100%;
  background-position: center center;
}

.img-slogan .bg-slogan:after {
  content: '';
  display: block;
  position: absolute;
  top: 15px;
  left: 15px;
  right: -15px;
  bottom: -15px;
  border: 2px solid var(--main-color);
}
</style>
