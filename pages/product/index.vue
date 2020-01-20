<template>
  <div class="product-page">
    <div class="row">
      <banner-page :title="'PROODCUTT PAGE'" />
      <breadcrumb :breadcrumb="propsBreadcrumb" />
      <div class="products-main grid">
        <div class="sidebar">
          <div class="search-product widget">
            <h4>Tìm sản phẩm</h4>
            <div>
              <input
                type="text"
                name=""
                placeholder="Tìm sản phẩm..."
              /><button>
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  width="18"
                  height="18"
                  viewBox="0 0 24 24"
                  fill="none"
                  stroke="currentColor"
                  stroke-width="2"
                  stroke-linecap="round"
                  stroke-linejoin="round"
                  class="feather feather-search"
                >
                  <circle cx="11" cy="11" r="8"></circle>
                  <line x1="21" y1="21" x2="16.65" y2="16.65"></line>
                </svg>
              </button>
            </div>
          </div>
          <div class="categories widget">
            <h4>Categories</h4>
            <!-- <ul>
              <li>
                <a
                  href="javascript:;"
                  class="js-category-sidebar active"
                  data-category-id="0"
                  >Đồng Hồ</a
                >
              </li>
              <li>
                <a
                  href="javascript:;"
                  class="js-category-sidebar "
                  data-category-id="3"
                  >Đồng hồ gỗ chữ nhật</a
                >
              </li>
              <li>
                <a
                  href="javascript:;"
                  class="js-category-sidebar "
                  data-category-id="4"
                  >Đồng hồ hình trụ đứng</a
                >
              </li>
              <li>
                <a
                  href="javascript:;"
                  class="js-category-sidebar "
                  data-category-id="5"
                  >Đồng hồ gỗ hình vuông</a
                >
              </li>
            </ul> -->
            <sidebar-categories :categories="categories" />
          </div>
        </div>
        <div class="product-list-view grid"></div>
      </div>
    </div>
  </div>
</template>

<script>
import BannerPage from '~/components/BannerPage.vue'
import Breadcrumb from '~/components/Breadcrumb.vue'
import SidebarCategories from '~/components/category/SidebarCategories.vue'

export default {
  transition: 'default',
  components: {
    BannerPage,
    Breadcrumb,
    SidebarCategories
  },

  asyncData() {
    return new Promise((resolve) => {
      // eslint-disable-next-line nuxt/no-timing-in-fetch-data
      setTimeout(function() {
        resolve({
          propsBreadcrumb: [
            {
              name: 'Đồng hồ',
              link: '/product'
            }
          ],
          categories: [
            {
              id: 1,
              name: 'Đồng Hồ',
              parentId: 0
            },
            {
              id: 5,
              name: 'Đồng Hồ Vuông',
              parentId: 1
            },
            {
              id: 6,
              name: 'Đồng Hồ Chữ Nhật',
              parentId: 1
            },
            {
              id: 7,
              name: 'Đồng Hồ Trụ',
              parentId: 1
            },
            {
              id: 9,
              name: 'Key Holder',
              parentId: 0
            },
            {
              id: 10,
              name: 'Hộp Khóa Mèo',
              parentId: 9
            },
            {
              id: 11,
              name: 'Hộp Khóa Cú',
              parentId: 9
            }
          ]
        })
      }, 10)
    })
  }
}
</script>
