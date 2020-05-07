<template>
  <div class="main-container">
    <div class="page-left-logo">
      <span class="page_left_logo__welcome">Добро пожаловать</span>
      <h1 class="page_left_logo__h1">ЯКИУДОН С КУРИЦЕЙ ТЕРИЯКИ СУШИ</h1>
      <div class="page_left_logo__h2">
        <h2>Жареная лапша, курица терияки, стручковая фасоль,</h2>
        <h2>ростки сои, болгарский перец, морковь</h2>
        <h2>Доставка суши круглосуточно</h2>
        <h2>Турбо доставка 29 минут</h2>
      </div>
    </div>
    <!-- Swiper -->
    <div class="main-slider">
      <div class="swiper-wrapper">
        <div class="swiper-slide main-slider-item">
          <img src="../assets/images/q1.jpg">
          <div class="swiper-slide-box-bottom">
            <div class="swiper-slide-box-bottom-text">Суши</div>
            <div class="swiper-slide-box-bottom-text2">муши</div>
          </div>
        </div>
        <div class="swiper-slide main-slider-item">
          <img src="../assets/images/q2.jpg">
          <div class="swiper-slide-box-bottom">
            <div class="swiper-slide-box-bottom-text">Суши</div>
            <div class="swiper-slide-box-bottom-text2">муши</div>
          </div>
        </div>
        <div class="swiper-slide main-slider-item">
          <img src="../assets/images/q1.jpg">
          <div class="swiper-slide-box-bottom">
            <div class="swiper-slide-box-bottom-text">Суши</div>
            <div class="swiper-slide-box-bottom-text2">муши</div>
          </div>
        </div>
        <div class="swiper-slide main-slider-item">
          <img src="../assets/images/q3.jpg">
          <div class="swiper-slide-box-bottom">
            <div class="swiper-slide-box-bottom-text">Суши</div>
            <div class="swiper-slide-box-bottom-text2">муши</div>
          </div>
        </div>
      </div>
      <!-- Add Pagination -->
      <div class="swiper-pagination"></div>
    </div>
    <!-- End Swiper -->
  </div>
</template>

<script>
  import Swiper from 'assets/js/swiper.min'
  import {gsap} from 'gsap'

  export default {
    mounted() {
      const timeLine = gsap.timeline()
      timeLine.to('.page-left-logo', 1, {opacity: 1})
        .from('.page_left_logo__welcome', .5, {opacity: 0, y: -100})
        .from('.page_left_logo__h1', .5, {opacity: 0, y: 100})
        .staggerFrom('.page_left_logo__h2 h2', .3, {opacity: 0, y: 100, onComplete: startSlide()}, .3)

      function startSlide() {
        const timeLine = gsap.timeline()
        timeLine.to('.page-left-logo', 1, {
          x: '-100%', opacity: 0, display: 'none', onComplete() {
            const swiper = new Swiper('.main-slider', {
              slidesPerView: 1,
              loop: true,
              spaceBetween: 10,
              // effect: 'fade',
              // initialSlide: 2,
              // init: false,
              /*pagination: {
                el: '.swiper-pagination',
                clickable: true,
              },*/
              breakpoints: {
                640: {
                  slidesPerView: 1,
                  spaceBetween: 10,
                },
                768: {
                  slidesPerView: 2,
                  spaceBetween: 20,
                },
                1024: {
                  slidesPerView: 4,
                  spaceBetween: 20,
                },
              }
            })
          }
        }, 4)
          .fromTo('.main-slider', .7, {opacity: 0, x: 800}, {opacity: 1, x: 0})
      }


    }
  }
</script>

<style>
  .main-container {
    display: flex;
  }

  .page-left-logo {
    opacity: 0;
    display: flex;
    flex-direction: column;
    justify-content: center;
    height: 100vh;
  }

  .page_left_logo__welcome {
    margin-bottom: 30px;
  }

  .page_left_logo__h1 {
    font-family: '2';
    font-size: 70px;
  }

  .main-slider {
    overflow: hidden;
    width: 100%;
    margin-top: 100px;

    position: relative;
    opacity: 0;
  }

  .swiper-wrapper {
    align-items: center;
  }

  .swiper-slide {
    display: flex;
    flex-wrap: wrap;
    justify-content: space-around;
    background: #7F828B;
    overflow: hidden;
  }

  .swiper-slide img {
    width: 800px;
  }

  .swiper-slide-box-bottom {
    position: absolute;
    left: 0;
    right: 0;
    bottom: 0;
    height: 100px;
    background: rgba(0, 0, 0, .5);
  }

  .swiper-slide-box-bottom-text {
    color: #fff;
    font-size: 30px;
    text-align: center;
  }

  .swiper-slide-box-bottom-text2 {
    color: #fff;
    font-size: 24px;
  }

  @media screen and (max-width: 767px){
    .page_left_logo__h1 {
      font-size: 50px;
    }
    .page_left_logo__h2{
      font-size: 18px;
    }
    .header__nav {
      font-size: 16px;
      padding: 5px 10px;
    }
  }
</style>
