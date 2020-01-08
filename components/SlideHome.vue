<template>
  <div class="container-slideshow">
    <div class="row">
      <div class="slideshow">
        <transition name="fade">
          <a
            :key="currentImg"
            :style="{ 'background-image': 'url(' + currentImg + ')' }"
            class="item-slide"
            href="javascript:;"
          >
          </a>
        </transition>
        <a @click="prev" class="prev">❮</a>
        <a @click="next" class="next">❯</a>
        <div class="item-dot">
          <span
            v-for="(item, index) in images"
            :key="item"
            :class="{ active: index == currentIndex }"
            @click="jumpImg(index)"
          ></span>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      images: [
        'http://moonearthvn.com/assets/upload/handmade/slide/10-1572419087175.jpg',
        'http://moonearthvn.com/assets/upload/handmade/slide/9-1572418084831.jpg'
      ],
      currentIndex: 0,
      timer: null
    }
  },

  computed: {
    currentImg() {
      return this.timer == null ? '' : this.images[this.currentIndex]
    }
  },

  mounted() {
    this.startSlide()
  },

  methods: {
    startSlide() {
      clearInterval(this.timer)
      this.timer = setInterval(this.next, 4000)
    },

    next() {
      this.currentIndex =
        this.currentIndex + 1 >= this.images.length ? 0 : this.currentIndex + 1
      this.startSlide()
    },
    prev() {
      this.currentIndex =
        this.currentIndex - 1 < 0
          ? this.images.length - 1
          : this.currentIndex - 1
      this.startSlide()
    },
    jumpImg(pos) {
      this.currentIndex = pos
      this.startSlide()
    }
  }
}
</script>

<style scoped>
.slideshow {
  position: relative;
  padding-top: 41%;
  overflow: hidden;
}

.item-slide {
  position: absolute;
  top: 0;
  bottom: 0;
  left: 0;
  right: 0;
  background-size: cover;
  background-repeat: no-repeat;
  background-position: center;
}

.fade-enter-active,
.fade-leave-active {
  transition: all 1s ease;
  overflow: hidden;
  visibility: visible;
  width: 100%;
  opacity: 1;
}

.fade-enter,
.fade-leave-to {
  visibility: hidden;
  width: 100%;
  opacity: 0;
}

.prev,
.next {
  cursor: pointer;
  position: absolute;
  top: 50%;
  transform: translateY(-50%);
  width: auto;
  padding: 16px;
  color: #fff;
  font-weight: bold;
  font-size: 18px;
  transition: all 0.5s;
  border-radius: 0 3px 3px 0;
  user-select: none;
}

.next {
  right: 0;
  border-radius: 3px 0 0 3px;
}

.prev {
  left: 0;
}

.slideshow:hover .prev,
.slideshow:hover .next {
  background-color: rgba(0, 0, 0, 0.5);
}

.item-dot {
  position: absolute;
  bottom: 10px;
  left: 0;
  right: 0;
  text-align: center;
  user-select: none;
}

.item-dot span {
  cursor: pointer;
  height: 15px;
  width: 15px;
  margin: 0 4px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  transition: all 0.2s;
}
.item-dot span.active {
  background-color: #717171;
}
.item-dot span:hover {
  border: 1px solid #666;
}
</style>
