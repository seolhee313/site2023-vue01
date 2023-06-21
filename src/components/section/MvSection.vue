<template>
  <section id="mvSection" :class="attr">
    <h3>뮤직비디오 구경하기</h3>
    <p>
      음악의 감동을 두배로! 영상으로 즐기는 음악! 뮤직비디오를 감상해보세요.
    </p>
    <div class="mv__inner container">
      <div class="mv__btn">
        <ul>
          <li><router-link to="/" class="active">K-pop</router-link></li>
          <li><router-link to="/">Pop</router-link></li>
          <li><router-link to="/">Hip-hop</router-link></li>
          <li><router-link to="/">R&B</router-link></li>
        </ul>
      </div>
      <div class="mv__conts">
        <div class="mv" v-for="(text, index) in texts" :key="index">
          <figure class="mv__header">
            <router-link to="https://www.youtube.com/watch?v=7HDeem-JaSY"
              ><img :src="text.img" :alt="'아이들' + (index + 1)"
            /></router-link>
          </figure>
          <div class="mv__body">
            <div class="pic">
              <img :src="text.icon" alt="아이들" />
            </div>
            <div class="title">
              <h4>{{ text.title }}</h4>
              <span>{{ text.desc }}</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<script>
export default {
  props: {
    attr: String,
  },
  data: function () {
    return {
      texts: [
        {
          img: "./images/mv/mv01.svg",
          title: "(여자)아이들((G)I-DLE) - 퀸카",
          desc: "조회수 9543만회 · 2주 전",
          icon: "./images/mv/mv01_01.svg",
        },
        {
          img: "./images/mv/mv02.svg",
          title: "aeapa 에스파 'Spicy' MV",
          desc: "조회수 7976만회 · 3주 전",
          icon: "./images/mv/mv02_01.svg",
        },
        {
          img: "./images/mv/mv03.svg",
          title: "IVE 아이브 'Kitsch' MV",
          desc: "조회수 6967만회 · 2개월 전",
          icon: "./images/mv/mv03_01.svg",
        },
        {
          img: "./images/mv/mv04.svg",
          title: "LE SSERAFIM (르세라핌) 'UNFORGIVEN'",
          desc: "조회수 7146만회 · 4주 전",
          icon: "./images/mv/mv04_01.svg",
        },
        {
          img: "./images/mv/mv05.svg",
          title: "BLACKPINK - ‘Pink Venom’ M/V",
          desc: "조회수 6.4억회 · 9개월 전",
          icon: "./images/mv/mv05_01.svg",
        },
        {
          img: "./images/mv/mv06.svg",
          title: "NewJeans (뉴진스) 'Attention' MV",
          desc: "조회수 4918만회 · 10개월 전",
          icon: "./images/mv/mv06_01.svg",
        },
      ],
    };
  },
};
</script>

<style lang="scss">
// mv__wrap
.mv__wrap {
}
.mv__inner {
  // display: flex;

  .mv__btn {
    margin-bottom: 30px;

    ul {
      display: flex;
      justify-content: center;

      li {
        a {
          border: 1px solid #000;
          display: inline-block;
          padding: 5px 20px;
          margin: 0 5px;
          border-radius: 40px;
          transition: background-color 0.3s;

          &.active {
            // border-width: 2px;
            background-color: #83a5f9;
            color: var(--color_white);
          }
          &:hover {
            background-color: #c8d8ff;
          }
        }
      }
    }
  }
  .mv__conts {
    @include flex-between;
    flex-wrap: wrap;

    .mv {
      width: 32.2222%;
      margin-bottom: 30px;

      .mv__body {
        display: flex;
        align-items: center;
        margin-top: 10px;

        .pic {
          margin-right: 10px;
          width: 50px;
          height: 50px;

          img {
            border-radius: 50%;
          }
        }
        .title {
          h4 {
            font-size: 20px;
            color: var(--color_body);
          }
          span {
            font-size: 16px;
            color: #243a4b;
          }
        }
      }

      img {
        border-radius: 10px;
        width: 100%;
      }

      &:nth-child(4) {
        margin-bottom: 0;
      }
      &:nth-child(5) {
        margin-bottom: 0;
      }
      &:nth-child(6) {
        margin-bottom: 0;
      }
    }
  }
}
</style>
