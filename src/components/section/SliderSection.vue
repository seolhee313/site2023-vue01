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
                <a :class="`more${index + 1}`" :href="slider.link"
                  >더 알아보기</a
                >
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
          title: "SeolHee<br /><em>Music</em>",
          desc: "음악은 우리의 감정을 자유롭게 표현하고, 일상 속에서 우리를 위로하며,<br />새로운 세계로 데려다 주는 힘이 있습니다.<br />이제 우리는 즐기는 음악을 위해 새로운 온라인 음악 사이트를 소개합니다.",
          image1: "./images/icon/icon01.png",
          image2: "./images/icon/icon12.svg",
          image3: "./images/icon/icon11.svg",
          link: "/intro",
        },
        {
          title: 'SeolHee<br /><em class="youtube">Youtube</em>',
          desc: "음악을 더욱 즐기는 방법으로 유튜브 페이지를 경험해 보세요.<br />여러분의 마음을 울릴 멋진 음악과 함께,<br />흥미로운 발견과 새로운 음악 여행을 시작해 보세요.",
          image1: "./images/icon/icon09.png",
          image2: "./images/icon/icon08.png",
          image3: "./images/icon/icon10.png",
          link: "/youtube",
        },
        {
          title: 'SeolHee<br /><em class="movie">Movie</em>',
          desc: "여러분의 영화 관람을 더욱 특별하게 만들어 줄 페이지를 소개합니다.<br />이곳은 다양한 장르와 감동적인 이야기가 담긴 영화들을 제공합니다.<br />최신 영화부터 오래된 클래식 영화까지 다양한 선택지를 찾아볼 수 있습니다.",
          image1: "./images/icon/icon02.png",
          image2: "./images/icon/icon03.png",
          image3: "./images/icon/icon04.png",
          link: "/movie",
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
@import "../../assets/scss/setting/mixins.scss";
// slider__wrap
.swiper {
  padding: 20px 0 50px;
}
.slider__inner {
  position: relative;
  // height: 700px;

  .slider__img {
    .slider {
      .text {
        h3 {
          font-size: 110px;
          font-weight: 800;
          text-transform: uppercase;
          line-height: 1;
          margin-bottom: 40px;
          padding-top: 110px;

          em {
            color: #4857ec;
          }
          .youtube {
            color: #ff3344;
          }
          .movie {
            color: #00c183;
          }
        }
      }
      p {
        font-size: 24px;
        line-height: 1.3;
        margin-bottom: 50px;
      }
      a {
        padding: 10px 30px;
        cursor: pointer;
      }
      .more1 {
        font-size: 18px;
        margin-bottom: 100px;
        border-radius: 50px;
        background-color: #fff;
        border: 2px solid #4857ec;
        color: #4857ec;

        &:hover {
          background-color: #4857ec;
          color: #fff;
        }
      }
      .more2 {
        font-size: 18px;
        margin-bottom: 100px;
        border-radius: 50px;
        background-color: #fff;
        border: 2px solid #ff3344;
        color: #ff3344;

        &:hover {
          background-color: #ff3344;
          color: #fff;
        }
      }
      .more3 {
        font-size: 18px;
        margin-bottom: 100px;
        border-radius: 50px;
        background-color: #fff;
        border: 2px solid #00c183;
        color: #00c183;

        &:hover {
          background-color: #00c183;
          color: #fff;
        }
      }
    }

    .img {
      position: absolute;
      right: 0;
      top: 0;
      width: 600px;
      height: 600px;
      background-image: url(../../assets/images/icon/iconbg.png);
      background-size: cover;

      img {
        &:nth-child(1) {
          position: absolute;
          width: 300px;
          right: -40px;
          top: 130px;
        }
        &:nth-child(2) {
          position: absolute;
          width: 250px;
          bottom: 10px;
          left: 110px;
        }
        &:nth-child(3) {
          position: absolute;
          width: 330px;
          top: 2px;
          left: -30px;
        }
        &.camera {
          position: absolute;
          width: 320px;
          top: 40px;
          left: -30px;
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
        left: 104%;
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
