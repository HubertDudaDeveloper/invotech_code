<template>
    <div id="slider">
        <carousel :per-page="1" v-bind:autoplay="true" v-bind:loop="true">
            <slide v-for="(slide, id) in slides" :key="id">
                <DesktopSlide :active="slide.id === i" :slide="slide" :i="passId"/>
            </slide>
        </carousel>
    </div>
</template>
<script>
import DesktopSlide from './slide/Slide.vue'
import { Carousel, Slide } from 'vue-carousel'

export default {
  name: 'DesktopSlider',
  data: () => ({
    i: 1,
    slides: [
      {
        id: 1,
        img: 'Bitmapv.png',
        title: '<div>Rabat 10%<a> na</a></div>pierwsze zamówienie!',
        body: 'Do 20 stycznia złóż zamówienie na stronie i<br>skorzystaj z promocji -10%. Spiesz się, czas<br>trwania promocji do końca lutego.',
        button: 'Zamów online'
      },
      {
        id: 2,
        img: 'Bitmapv.png',
        title: '<div>Rabat 10%<a> na</a></div>pierwsze zamówienie!',
        body: 'Do 20 stycznia złóż zamówienie na stronie i<br>skorzystaj z promocji -10%. Spiesz się, czas<br>trwania promocji do końca lutego.',
        button: 'Zamów online'
      },
      {
        id: 3,
        img: 'Bitmapv.png',
        title: '<div>Rabat 10%<a> na</a></div>pierwsze zamówienie!',
        body: 'Do 20 stycznia złóż zamówienie na stronie i<br>skorzystaj z promocji -10%. Spiesz się, czas<br>trwania promocji do końca lutego.',
        button: 'Zamów online'
      }
    ]
  }),
  methods: {
    handleClick (id) {
      this.i = id + 1
    }
  },
  computed: {
    passId () {
      return this.i
    }
  },
  components: {
    DesktopSlide,
    Carousel,
    Slide
  }
}
</script>
<style lang="scss">
@import url('https://fonts.googleapis.com/css2?family=Nunito+Sans:wght@400;700;800&display=swap');

.VueCarousel-dot-container {
    position: absolute;
    top: 495px;
    left: 140px;
    display: flex;
}
.VueCarousel-dot-container button {
    position: relative;
    background-image: url('./../../assets/Oval\ Copy\ 2.svg');
    height: 10px;
    width: 10px;
    margin: 0px 0px;
    background-size: contain;
}
button.VueCarousel-dot--active {
    background-image: url('./../../assets/Oval\ Copy\ 5.svg')
}

#slider {
  max-width: 100vw;
}

@media screen and (max-width: 1050px) {
  .VueCarousel-pagination {
    display: none;
  }
  #slide {
    display: grid;
  }
  .slide__img {
    visibility: hidden;
  }
  .slide__article {
    width: 100vw;
    align-items: center;
    h1 {
      font-size: 39px;
    }
    p,
    h1,
    button {
      margin: 15px 0px;
      line-height: unset;
    }
  }
}
</style>
