<template>
  <div class="home">
    <!-- <swiper class="mySwiper" :options='swiperOption' ref="mySwiper">
      <swiper-slide v-for="(item,index) in images" :key="index">
        <img :src="item"> 
      </swiper-slide> 
      <div class="swiper-pagination" slot="pagination"></div>
      <div class="swiper-button-prev" slot="button-prev"></div>
      <div class="swiper-button-next" slot="button-next"></div>
    </swiper> -->
    <test></test>
  </div>
</template>

<script>
const images = require.context('../assets/images',false,/\.(png|jpg)$/i);
const imagesList = images.keys().map(item => images(item));
import { swiper, swiperSlide } from "vue-awesome-swiper";
import Test from './test.vue'
export default {
  name: "Home",
  data() {
    return {
      images: imagesList,
      swiperOption: {
        autoplay: {
          delay: 3000,
          //用户触碰到之后不会停止轮播图切换
          disableOnInteraction: false,
        },
        loop: true,
        speed: 1000,
        // 小圆点
        pagination: {
          el: '.swiper-pagination',
          clickable: true
        },
        // 前后切换按钮
        navigation: {
          nextEl: '.swiper-button-next',
          prevEl: '.swiper-button-prev'
        }
      }
    };
  },
  computed: {
    swiper() {
      // 获取到swiper的对象
      return this.$refs.mySwiper.swiper;
    }
  },
  destroy() {
    // 可以在任意的地方调用，swiper对象上的方法
    console.log(this.swiper);
    // 销毁swiper对象，
    this.swiper.destroy(true);
  },
  components: {
    swiper,
    swiperSlide,
    Test
  },
};
</script>

<style scoped>
.swiper-container {
  position: relative;
  width: 100%;
}

.swiper-container img {
  width: 100%;
}

.swiper-container >>> .swiper-pagination-bullet {
  background:  #676767;
}

.swiper-container >>> .swiper-pagination-bullet-active {
  background:#ffaf00;
}

.swiper-container >>> .swiper-button-prev, 
.swiper-container >>> .swiper-button-next {
  border: none;
  outline: none;
}


p {
  font-size: 50px;
  color: black;
}


</style>