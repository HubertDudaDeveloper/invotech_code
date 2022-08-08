<template>
    <div id="slide"  >
       <div class="slide__article">
            <h1 v-html="slide.title"></h1>
            <p v-html="slide.body"></p>
            <button>{{ slide.button }}</button>
        </div>
        <div class="slide__img"></div>
    </div>
</template>
<script>
export default {
  name: 'DesktopSlide',
  data: () => ({
  }),
  props: [
    'slide',
    'i'
  ]
}
</script>
<style lang="scss">
#slide {
    height: 615px;
    width: 100vw;
    display: flex;
}
.slide__article {
    width: 50%;
    background-color: white;
    display: flex;
    align-items: flex-start;
    flex-direction: column;
    margin-top: 108px;

    h1,
    p,
    button {
        margin: 0px 0px 35px 150px
    }
}
.slide__img {
    width: 50%;
    background-image: url('@/assets/Bitmapv.png');
    background-repeat: no-repeat;
}
h1 {
    font-family: 'Nunito Sans', sans-serif;
    font-size: 51px;
    font-weight: 800;
    line-height: 53px;
    letter-spacing: 2px;
    text-align: left;

    div {
        width: fit-content;
        height: 52px;
        background-color: black;
        color: white;
        margin-bottom: 15px;
        a {
            background-color: white;
            color: black;
        }
}
}
p {
    font-family: 'Nunito Sans', sans-serif;
    font-size: 20px;
    font-weight: 600;
    line-height: 25px;
    letter-spacing: 0px;
    text-align: left;
}
button {
    width: 204px;
    height: 49px;
    font-family: 'Nunito Sans', sans-serif;
    font-style: normal;
    font-weight: 400;
    font-size: 14.4px;
    line-height: 14px;
    text-align: center;
    color: #FFFFFF;
    background: #920303;
    border-radius: 10px;
    border: none;
    cursor: pointer;
    transition-duration: 0.5s;
    &:hover {
      transform:scale(1.1);
    }
}
</style>
