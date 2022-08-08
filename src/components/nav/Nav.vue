<template>
<!-- Komponent nawigacja -->
    <div id="nav">
      <div class="nav__container">
        <img id="logo" src="@/assets/Object.png"/>
        <div class="container nav-container">
            <div class="hamburger-lines" @click="menu()">
              <span class="line line1"></span>
              <span class="line line2"></span>
              <span class="line line3"></span>
            </div>
            </div>
        <div id="nav__left" class="dnone">
          <navLeftButton v-for="(item, index) in nav.nav_Left" v-bind:key="index"  :item="item" />
        </div>
        <div id="nav__right" class="dnone">
          <navRightButton v-for="(item, index) in nav.nav_Right" v-bind:key="index"  :item="item" />
        </div>
      </div>
    </div>
</template>
<script>
import navLeftButton from './buttons/Left.vue'
import navRightButton from './buttons/Right.vue'

export default {
  name: 'DesktopNav',
  components: {
    navLeftButton,
    navRightButton
  },
  methods: {
    menu () {
      document.getElementById('nav').classList.toggle('fullh')
      document.getElementById('nav__left').classList.toggle('dnone')
      document.getElementById('nav__right').classList.toggle('dnone')
    }
  },
  data: () => ({
    nav: {
      nav_Left: [
        { name: 'Steaks' },
        { name: 'Burgers' },
        { name: 'French fries' },
        { name: 'Drinks' },
        { name: 'Gdzie dowozimy?' },
        { name: 'Kontakt' }
      ],
      nav_Right: [
        { name: 'Moje konto', icon: 'mojekonto.svg' },
        { name: 'Koszyk', icon: 'koszyk.svg' },
        { name: 'Zamów', icon: 'zamow_ikona.svg' }
      ],
      href: [null]
    }
  })
}
</script>
<style lang="scss">
#nav {
  background-color: white;
  width: 100vw;
  display: flex;
  justify-content: center;
  box-shadow: 0px -15px 20px grey;
  }
.nav__container {
  width: 85%;
  height: 81px;
  display: flex;
  align-items: center;
  justify-content: center;
  gap: 70px;
  font-family: 'system-ui';
  font-style: normal;
  font-weight: 600;
  font-size: 14px;
  line-height: 24px;
  background-color: white;
  }
  #logo {
    flex-grow: 0;
    object-fit: none;
    transition-duration: 0.5s;
    &:hover {
      transform:scale(1.1);
    }
  }
  #nav__left {
    flex-grow: 6;
    display: flex;
    gap: 53px;
    a {
      color: black;
      text-decoration: none;
      transition-duration: 0.5s;
      &:hover {
        color: #920303;
      }
    }
  }
  #nav__right {
    flex-grow: 3;
    display: flex;
    justify-content: flex-end;
}
@media screen and (max-width: 1050px) {
  #nav {
    height: auto;
    position: sticky;
    top: 0px;
    background-color: white;
    z-index: 99;
  }
  .nav__container {
  display: grid;
  justify-items: center;
  }
  #nav__left {
    display: grid;
    justify-items: center;
  }
  #nav__right {
    display: grid;
    justify-items: center;
    gap: 20px;
  }
  .btn:last-child a {
      margin: 0px 0px 0px 0px;
  }
  .dnone {
    display: none !important;
  }
  .fullh {
    height: 100vh !important;
  }
  .nav-container .hamburger-lines {
    cursor: pointer;
    display: block;
    height: 26px;
    width: 32px;
    position: absolute;
    top: 17px;
    right: 20px;
    z-index: 99;
    display: flex;
    flex-direction: column;
    justify-content: space-between;
  }

  .nav-container .hamburger-lines .line {
    display: block;
    height: 4px;
    width: 100%;
    border-radius: 10px;
    background: #0e2431;
  }

  .nav-container .hamburger-lines .line1 {
    transform-origin: 0% 0%;
    transition: transform 0.4s ease-in-out;
  }

  .nav-container .hamburger-lines .line2 {
    transition: transform 0.2s ease-in-out;
  }

  .nav-container .hamburger-lines .line3 {
    transform-origin: 0% 100%;
    transition: transform 0.4s ease-in-out;
  }

}
</style>
