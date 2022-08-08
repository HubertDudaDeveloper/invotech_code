<template>
    <div id="box" :style="{backgroundImage:`url(${img})`}">
      <div class="container">
        <h2>{{ item.title }}</h2>
        <p v-html="item.body"></p>
        <a href="" ><button>{{ item.button }}</button></a>
      </div>
    </div>
</template>
<script>
export default {
  name: 'AdsBox',
  props: [
    'img',
    'item'
  ]
}
</script>
<style lang="scss">
#box {
  width: 47.25%;
  height: 405px;
  padding: 5px;
  background-color: black;
  color: white;
  border-radius: 7px;
  background-size: cover;
  display: flex;
  flex-direction: column;
  justify-content: center;
  .container {
    padding: 0px 120px 0px;
    width: 330px;
    font-family: 'Nunito Sans', sans-serif;
    h2 {
      font-weight: 700;
      font-size: 35px;
      line-height: 32px;
    }
    p {
      font-weight: 400;
      font-size: 20px;
      line-height: 32px;
      div{
        display: flex;
        .black {
          background-color: black;
          width: 53px;
          height: 25px;
        }
        .red {
          background-color: #920303;
          width: 103px;
          height: 28px;
        }
        .black ,.red {
          align-items: center;
          justify-content: center;
          margin: 0px 5px;
        }
        img {
          padding: 10px 12px 0px 0px;
        }
      }
    }
    button {
     margin-bottom: 50px;
    }
  }
}
</style>
