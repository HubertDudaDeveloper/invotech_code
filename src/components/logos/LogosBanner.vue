<template>
    <div id="logos">
        <div v-for="(logo, i) in logos" v-bind:key="i" class="logo__banner">
            <img v-bind:src="require('@/assets/' + logo.banner)" :alt="logo.name">
        </div>
    </div>
</template>
<script>
export default {
  name: 'LogosBanner',
  data: () => ({
    logos: [
      { name: 'Pyszne.pl', banner: 'Bitmap-4.png' },
      { name: 'DeliGoo', banner: 'e.png' },
      { name: 'Glovo', banner: 'Bitmap.png' },
      { name: 'UberEats', banner: 'Bitmap-2.png' },
      { name: 'BoltFood', banner: 'Bitmap-3.png' }
    ]
  })
}
</script>
<style lang="scss">
#logos {
    width: 71vw;
    height: 80px;
    display: flex;
    align-items: center;
    justify-content: space-around
}
@media screen and (max-width: 600px) {
  #logos {
    width: 95vw;
    overflow-x: hidden;
  }
  .logo__banner {
  padding: 0vw 5vw;
  position: relative;
  animation: logos 20s infinite;
  }
}
@keyframes logos {
    0% {left: 20vw;}
    50% {left: -30vw;}
    100% {left: 20vw;}
  }

</style>
