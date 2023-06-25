<template>
  <section id="unsplashSection" :class="attr">
    <div class="unsplash__inner container">
      <div class="unsplash__text">
        <h3>음악 이미지 다운로드</h3>
        <p>
          음악에 관련된 이미지들을 고화질로 다운로드 받을 수 있습니다.
          <br />
          상업적 이용은 피해주세요!
        </p>
        <router-link to="/unsplash" class="button-green">
          자세히 보기
        </router-link>
      </div>
      <div class="unsplash__item">
        <div>
          <img
            src="@/assets/images/unsplash/unsplash04.png"
            alt="unsplashIMG"
          />
        </div>
        <div>
          <img
            src="@/assets/images/unsplash/unsplash03.png"
            alt="unsplashIMG"
          />
        </div>
        <div>
          <img
            src="@/assets/images/unsplash/unsplash02.png"
            alt="unsplashIMG"
          />
        </div>
        <div>
          <img
            src="@/assets/images/unsplash/unsplash01.png"
            alt="unsplashIMG"
          />
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
};
</script>

<style lang="scss">
@import "../../assets/scss/setting/mixins.scss";
// unsplash__wrap
.unsplash__wrap {
  overflow: hidden;
}
.unsplash__inner {
  height: 600px;
  .unsplash__text {
    h3 {
      font-size: 50px;
      margin-bottom: 40px;
    }
    p {
      font-size: 22px;
      font-weight: 300;
      margin-bottom: 60px;
    }
    a {
      @include border(50px);
    }
  }
  .unsplash__item {
    @include flex-between;
    margin-top: 70px;
    position: absolute;
    > div {
      width: 413px;
      img {
        width: 100%;
        padding: 0 20px 0 0;
        @include border(20px);
      }
    }
  }
}

// unsplash__page
.unsplash__cont {
  ul {
    column-count: 4;
    li {
      margin-bottom: 20px;
    }
  }
}

// unsplash__search
.unsplash__search {
  text-align: center;
  margin-bottom: 50px;
  margin-top: 70px;
  input {
    border: 1px solid #e8ecf2;
    font-size: 16px;
    padding: 10px 20px;
    border-radius: 50px;
    min-width: 300px;
    margin-right: 10px;
  }
  button {
    @include button(#4857ec, #fff);
    border-radius: 50px;
  }
}

.unsplash__slider {
  a {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;

    img {
      width: 50%;
      height: 650px;
    }
  }
}

.unsplash__tag {
  ul {
    display: flex;
    justify-content: center;
    margin-top: 100px;
    margin-bottom: 50px;

    li {
      button {
        border: 1px solid #4857ec;
        padding: 10px 20px;
        margin: 0 10px;
        color: #4857ec;
        background-color: #fff;
      }
    }
  }
}
</style>
