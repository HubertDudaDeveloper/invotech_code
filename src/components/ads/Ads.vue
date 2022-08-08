<template>
    <div id="ads">
        <AdsBox v-for="(item, index) in ads" v-bind:key="index" :item="item" :img="require('@/assets/' + item.img)" />
    </div>
</template>
<script>
import AdsBox from './box/Box.vue'

export default {
  name: 'AdsContainer',
  data: () => ({
    ads: {
      boxOne: {
        img: 'dana-devolk-x2cNcfz_xXU-unsplash.png',
        title: 'Zestaw dla 3 osób',
        body: 'Razem smakuje lepiej! Zamów<br> zestawy obiadowy dla 3 osób <div>już od <div class="black"> 39zł</div></div>',
        button: 'Zamów online'
      },
      boxTwo: {
        img: 'aplikacja.png',
        title: 'UberEats',
        body: '<div>Zamawiaj w aplikacji <div class="red">10% taniej.</div></div> Pobierz aplikacje UberEats już dziś. <div class="shops"><a href="" ><img src="Group 4.svg"></a><a href=""><img src="App_Store_(iOS).svg"></a><a href="" ><img src="huawei-app-badge-9757fa 2.svg"></a><div/>',
        button: 'Zamów online'
      }
    }
  }),
  components: {
    AdsBox
  }
}
</script>
<style lang="scss">
#ads {
  width: 100vw;
  display: flex;
  justify-content: center;
  gap: 16px;
}
.shops img {
  transition-duration: 0.5s;
    &:hover {
      transform:scale(1.1);
    }
}

@media screen and (max-width: 1050px) {
  #ads {
    flex-direction: column;
    align-items: center;
  }
  #box {
    width: 95vw;
    align-items: center;
    .container {
      padding: 0px;
    }
  }
}
</style>
