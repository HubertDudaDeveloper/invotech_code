<template>
    <div class="btn">
        <a href="">
            <img v-bind:src="require('@/assets/' + item.icon)" :alt="item.name">
            {{item.name}}
        </a>
    </div>
</template>
<script>
export default {
  name: 'navButtonRight',
  props: ['item']
}
</script>
<style lang="scss">
.btn a {
    width: 97px;
    height: 57px;
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    color: black;
    text-decoration: none;
    transition-duration: 0.5s;
    &:hover {
      transform:scale(1.05);
      color: #920303;
    }
}
.btn:last-child a {
    background: #920303;
    border-radius: 10px;
    color: white;
    margin: 0px 0px 0px 15px;
}
</style>
