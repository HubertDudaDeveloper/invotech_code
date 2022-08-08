<template>
  <div id="app">
    <DesktopNav />
    <DesktopSlider />
    <LogosBanner />
    <AdsContainer />
  </div>
</template>

<script>
import DesktopNav from './components/nav/Nav.vue'
import DesktopSlider from './components/slider/Slider.vue'
import LogosBanner from './components/logos/LogosBanner.vue'
import AdsContainer from './components/ads/Ads.vue'

export default {
  name: 'App',
  components: {
    DesktopNav,
    DesktopSlider,
    LogosBanner,
    AdsContainer
  }
}
</script>

<style lang="scss">
body {
  margin: 0px;
}

#app {
  background-color: white;
  margin: 0;
  display: flex;
  justify-items: center;
  flex-direction: column;
  align-items: center;
}
@media screen and (max-width: 1050px) {
  div {
    max-width: 93vw;
  }
}
</style>
