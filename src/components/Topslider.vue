<template>
  <div class="container my-3">
    <!-- Slider main container -->
    <div class="swiper-container" id="topSwiper">
      <!-- Additional required wrapper -->
      <div class="swiper-wrapper">
        <!-- Slides -->
        <div class="swiper-slide" v-for="(item, index) in sliderImg" :key="index">
          <div
            class="slide h-100"
            style="background-size: cover; background-repeat: no-repeat; background-position: center;"
            :style="{backgroundImage: `url(${item.imgUrl})`}"
            :title="`${item.title}`"
          ></div>
        </div>
      </div>
      <!-- If we need pagination -->
      <div class="swiper-pagination"></div>

      <!-- If we need navigation buttons -->
      <div class="swiper-button-prev"></div>
      <div class="swiper-button-next"></div>
    </div>
  </div>
</template>

<script>
import Swiper from "swiper";
export default {
  data: function() {
    return {
      sliderImg: [
        {
          imgUrl: "./static/sliderImg/sen4.png",
          title: "英雄傳說 閃之軌跡 IV -THE END OF SAGA-"
        },
        {
          imgUrl: "./static/sliderImg/monster.jpeg",
          title: "魔物獵人 世界 モンスターハンター：ワールド"
        },
        {
          imgUrl: "./static/sliderImg/resident_evil2.png",
          title: "惡靈古堡2 重製版"
        }
      ]
    };
  },
  mounted() {
    var mySwiper = new Swiper("#topSwiper", {
      // Optional parameters
      direction: "horizontal",
      loop: true,
      grabCursor: true,
      // centeredSlides : true,
      autoplay: {
        delay: 10000,
        disableOnInteraction: false
      },
      // If we need pagination
      pagination: {
        el: ".swiper-pagination",
        clickable: true
      },
      // Navigation arrows
      navigation: {
        nextEl: ".swiper-button-next",
        prevEl: ".swiper-button-prev"
      }
    });
  }
};
</script>

<style lang="scss" scoped>
.swiper-container {
  height: 250px;
  @media (min-width: 768px) {
    height: 400px;
  }
}
</style>