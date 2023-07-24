<template>
  <section id="memberSection" class="member__wrap section center">
    <h3>한국 대표 가수</h3>
    <p>한국을 대표하는 자랑스러운 가수들을 소개해드립니다.</p>

    <div class="member__inner container">
      <div class="member">
        <figure class="member__header">
          <img src="@/assets/images/member/bts01.svg" alt="멤버1" />
        </figure>
        <div class="member__body m1">
          <h4 class="title">BTS</h4>
          <!-- <p class="desc"></p> -->
          <router-link to="/" class="btn">자세히 보기</router-link>
        </div>
      </div>
      <div class="member">
        <figure class="member__header">
          <img src="@/assets/images/member/blackpink01.svg" alt="멤버2" />
        </figure>
        <div class="member__body m2">
          <h4 class="title">BLACK PINK</h4>
          <!-- <p class="desc"></p> -->
          <router-link to="/" class="btn">자세히 보기</router-link>
        </div>
      </div>
      <div class="member">
        <figure class="member__header">
          <img src="@/assets/images/member/psy01.png" alt="멤버3" />
        </figure>
        <div class="member__body m3">
          <h4 class="title">PSY</h4>
          <!-- <p class="desc"></p> -->
          <router-link to="/" class="btn">자세히 보기</router-link>
        </div>
      </div>
    </div>
  </section>
</template>

<style lang="scss">
// member__wrap
.member__wrap {
}
.member__inner {
  display: flex;
  justify-content: space-between;

  .member {
    width: 32%;
    position: relative;
    // border: 2px solid var(--color_body);

    .member__header {
      // margin-top: -20px;

      img {
        width: 100%;
      }
    }
    .member__body {
      // margin-top: -90px;
      position: absolute;
      left: 0;
      bottom: 0;
      width: 100%;
      padding: 15px 10px;
      background: #515151;
      color: var(--color_white);
      z-index: 100;
      text-align: center;

      h4 {
        font-size: 22px;
      }

      a {
        color: var(--color_white);
        text-decoration: underline;
        text-underline-position: under;
      }
    }
    .m1 {
      background: #9a89e0a5;
      transition: all 0.3s;

      &:hover {
        background-color: #9a89e0dc;
      }
    }
    .m2 {
      background: #eb4d4a8d;
      transition: all 0.3s;

      &:hover {
        background-color: #eb4d4aca;
      }
    }
    .m3 {
      background: #ffd6097f;
      transition: all 0.3s;

      &:hover {
        background-color: #ffd609cd;
      }
    }
  }
}
</style>
