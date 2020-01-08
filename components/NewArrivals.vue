<template>
  <div class="container-new-arrivals">
    <div class="row new-arrivals">
      <h2>New Arrivals</h2>
      <div class="grid products">
        <item-list-product
          v-for="(product, index) in products"
          :key="index"
          :product="product"
        />
      </div>
    </div>
  </div>
</template>

<script>
import ItemListProduct from '~/components/product/ItemListProduct.vue'
export default {
  components: {
    ItemListProduct
  },
  data() {
    return {
      products: [
        {
          images: [
            'http://moonearthvn.com/assets/upload/handmade/product-images/thumbnail/lucky-cat-large-clock-1566620877604.jpg'
          ],
          name: 'LUCKY CAT LARGE CLOCK',
          price: 2050000
        },
        {
          images: [
            'http://moonearthvn.com/assets/upload/handmade/product-images/thumbnail/lucky-cat-large-clock-1566620877604.jpg',
            'http://moonearthvn.com/assets/upload/handmade/product-images/thumbnail/elephant-large-clock-1566620719659.jpg'
          ],
          name: 'LUCKY CAT LARGE CLOCK',
          price: 2050000
        },
        {
          images: [
            'http://moonearthvn.com/assets/upload/handmade/product-images/thumbnail/lucky-cat-large-clock-1566620877604.jpg',
            'http://moonearthvn.com/assets/upload/handmade/product-images/thumbnail/elephant-large-clock-1566620719659.jpg'
          ],
          name: 'LUCKY CAT LARGE CLOCK',
          price: 2050000
        },
        {
          images: [
            'http://moonearthvn.com/assets/upload/handmade/product-images/thumbnail/lucky-cat-large-clock-1566620877604.jpg',
            'http://moonearthvn.com/assets/upload/handmade/product-images/thumbnail/elephant-large-clock-1566620719659.jpg'
          ],
          name: 'LUCKY CAT LARGE CLOCK',
          price: 2050000
        }
      ]
    }
  }
}
</script>

<style>
.new-arrivals h2 {
  border-bottom: 1px solid var(--main-color);
  padding-bottom: 12px;
  font-family: 'Playfair Display';
  font-weight: 400;
  margin-bottom: 25px;
}

.new-arrivals .grid.products {
  grid-template-columns: repeat(4, calc(25% - 30px));
  grid-gap: 40px;
  padding: 10px 0;
}
</style>
