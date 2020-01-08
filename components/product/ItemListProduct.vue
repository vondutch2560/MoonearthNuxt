<template>
  <div class="product-item">
    <a href="javascript:;" class="thumb-image">
      <div
        :style="{ 'background-image': 'url(' + thumbPrimary + ')' }"
        class="thumb-primary"
      ></div>
      <div
        :style="{ 'background-image': 'url(' + thumbSecondary + ')' }"
        class="thumb-secondary"
      ></div>
    </a>
    <h5>{{ product.name }}</h5>
    <span class="price">{{ priceFormat }}</span>
  </div>
</template>

<script>
export default {
  props: {
    product: {
      type: Object,
      default: () => []
    }
  },

  computed: {
    priceFormat() {
      return new Intl.NumberFormat('vi-VI', {
        style: 'currency',
        currency: 'VND'
      }).format(this.product.price)
    },

    thumbPrimary() {
      return this.product.images[0] === undefined ? '' : this.product.images[0]
    },

    thumbSecondary() {
      return this.product.images[1] === undefined ? '' : this.product.images[1]
    }
  }
}
</script>

<style>
.product-item {
  font-family: 'Varela Round';
  position: relative;
  border: 1px solid #eaeaea;
  padding-bottom: 20px;
  transition: border 0.2s;
}

.product-item .thumb-image {
  width: 100%;
  display: block;
  position: relative;
  text-align: center;
}

.product-item .thumb-image div {
  background-size: contain;
  background-position: center;
  background-repeat: no-repeat;
  transition: all 0.2s;
}

.product-item .thumb-image .thumb-primary {
  width: 100%;
  height: 0;
  padding-bottom: 100%;
  opacity: 1;
}

.product-item .thumb-image .thumb-secondary {
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  visibility: hidden;
  opacity: 0;
}

.product-item h5 {
  font-family: inherit;
  text-align: center;
  padding: 0 8px;
  line-height: 1.4;
  font-size: 14px;
  font-weight: normal;
  margin-bottom: 10px;
}

.product-item .price {
  width: 100%;
  display: block;
  text-align: center;
  color: var(--main-color);
}

.product-item:hover {
  border: 1px solid var(--main-color);
}

.product-item:hover .thumb-image .thumb-primary {
  opacity: 0.5;
}
.product-item:hover .thumb-image .thumb-secondary {
  opacity: 1;
  visibility: visible;
}
</style>
