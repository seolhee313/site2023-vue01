<template>
  <section id="sliderSection" :class="attr">
    <div class="slider__inner">
      <swiper
        :slides-per-view="1"
        :space-8between="50"
        navigation
        :pagination="{ clickable: true }"
        :autoplay="{
          delay: 3000,
          disableOnInteraction: false,
        }"
        :modules="modules"
        :loop="true"
        @swiper="onSwiper"
        @slideChange="onSlideChange"
      >
        <swiper-slide v-for="(slider, index) in sliders" :key="index">
          <div class="slider__img">
            <div class="slider s1 container">
              <div class="text">
                <h3 v-html="slider.title"></h3>
                <p v-html="slider.desc"></p>
                <a href="#" class="more button-red">더 알아보기</a>
              </div>
              <div class="img" aria-label="hidden">
                <img :src="slider.image2" alt="마이크" />
                <img :src="slider.image1" alt="유튜브" />
                <img :src="slider.image3" alt="헤드셋" />
              </div>
              <div class="circle" aria-label="hidden">
                <span class="circle c1"></span>
                <span class="circle c2"></span>
                <span class="circle c3"></span>
                <span class="circle c4"></span>
                <span class="circle c5"></span>
              </div>
            </div>
          </div>
        </swiper-slide>
      </swiper>
    </div>
  </section>
</template>
<script>
import { Autoplay, Navigation, Pagination } from "swiper";
import { Swiper, SwiperSlide } from "swiper/vue";
import "swiper/css";
import "swiper/css/navigation";
import "swiper/css/pagination";

export default {
  props: {
    attr: String,
  },
  data: function () {
    return {
      sliders: [
        {
          title: "SeolHee<br />Music",
          desc: "음악은 우리의 감정을 자유롭게 표현하고, 일상 속에서 우리를 위로하며,<br />새로운 세계로 데려다 주는 힘이 있습니다.<br />이제 우리는 즐기는 음악을 위해 새로운 온라인 음악 사이트를 소개합니다.",
          image1: "./images/icon/icon01.png",
          image2: "./images/icon/icon12.svg",
          image3: "./images/icon/icon11.svg",
        },
        {
          title: "SeolHee<br />Music",
          desc: "음악은 우리의 감정을 자유롭게 표현하고, 일상 속에서 우리를 위로하며,<br />새로운 세계로 데려다 주는 힘이 있습니다.<br />이제 우리는 즐기는 음악을 위해 새로운 온라인 음악 사이트를 소개합니다.",
          image1: "./images/icon/icon02.png",
          image2: "./images/icon/icon03.png",
          image3: "./images/icon/icon04.png",
        },
        {
          title: "SeolHee<br />Music",
          desc: "음악은 우리의 감정을 자유롭게 표현하고, 일상 속에서 우리를 위로하며,<br />새로운 세계로 데려다 주는 힘이 있습니다.<br />이제 우리는 즐기는 음악을 위해 새로운 온라인 음악 사이트를 소개합니다.",
          image1: "./images/icon/icon09.png",
          image2: "./images/icon/icon08.png",
          image3: "./images/icon/icon10.png",
        },
      ],
    };
  },
  components: {
    Swiper,
    SwiperSlide,
  },
  setup() {
    const onSwiper = (swiper) => {
      console.log(swiper);
    };
    const onSlideChange = () => {
      console.log("slide change");
    };
    return {
      onSwiper,
      onSlideChange,
      modules: [Autoplay, Navigation, Pagination],
    };
  },
};
</script>
<style lang="scss">
.swiper {
  overflow: visible;
}
.swiper-pagination {
  bottom: -80px !important;
}
.slider__inner {
  // overflow: hidden;
  position: relative;
  .slider__img {
    .slider {
      .text {
        h3 {
          font-size: 110px;
          font-weight: 800;
          text-transform: uppercase;
          line-height: 1;
          margin-bottom: 40px;
        }
        p {
          font-size: 24px;
          line-height: 1.3;
          margin-bottom: 50px;
        }
        .more {
          font-size: 18px;
        }
      }
      .img {
        position: absolute;
        right: 0;
        top: -120px;
        width: 600px;
        height: 600px;
        background-image: url(../../assets/images/icon/iconbg.png);
        background-size: cover;
        img {
          &:nth-child(1) {
            position: absolute;
            width: 300px;
          }
          &:nth-child(2) {
            position: absolute;
            width: 300px;
            right: 0;
            bottom: 140px;
          }
          &:nth-child(3) {
            position: absolute;
            width: 300px;
            bottom: 0;
            left: 30px;
          }
        }
      }
      .circle {
        span {
          display: block;
          position: absolute;
          left: 50%;
          top: 50%;
          width: 20px;
          height: 20px;
          border-radius: 50%;
        }
        span:nth-child(1) {
          background-color: var(--button_blue);
          left: 50%;
          width: 10px;
          height: 10px;
        }
        span:nth-child(2) {
          background-color: var(--button_red);
          top: 20%;
          left: -10%;
          width: 40px;
          height: 40px;
        }
        span:nth-child(3) {
          background-color: var(--button_green);
          left: 100%;
          top: 10%;
        }
        span:nth-child(4) {
          background-color: var(--button_red);
          left: 17%;
          top: -10%;
          width: 10px;
          height: 10px;
        }
        span:nth-child(5) {
          background-color: var(--button_blue);
          left: 90%;
          top: 80%;
          width: 30px;
          height: 30px;
        }
      }
    }
  }
  .slider__btn {
    > a {
      position: absolute;
      top: 50%;
      transform: translateY(-50%);
      width: 22px;
      height: 40px;
      transition: opacity 0.3s;
      &:hover {
        opacity: 0.5;
      }
    }
    .left {
      left: 20px;
      background-image: url(../../assets/images/slider/slider__left.png);
    }
    .right {
      right: 20px;
      background-image: url(../../assets/images/slider/slider__right.png);
    }
  }
  .slider__dot {
    position: absolute;
    left: 50%;
    bottom: -80px;
    transform: translateX(-50%);
    a {
      display: inline-block;
      width: 16px;
      height: 16px;
      border-radius: 50%;
      margin: 0 5px;
      border: 4px solid #ff3344;
      background-color: #ff3344;
      box-shadow: 0 0 0 3px transparent;
      &.active {
        box-shadow: 0 0 0 3px #ff3344;
        border-width: 4px;
        background-color: #fff;
      }
    }
  }
}
</style>
