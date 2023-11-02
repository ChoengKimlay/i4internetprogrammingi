<template>

  <div class="item" :style="{backgroundColor: Color}">
    <div class="image">
      <img :src=Img alt="">
    </div>
    <div class="food">
      <div class="title">{{ Title }}</div>
      <div class="item2">{{ Item }}</div>
    </div>
  </div>

</template>

<script>

export default {
  name: "Category",
  props: {
    Img: String,
    Title: String,
    Item: String,
    Color: String
  }
}

</script>

<style scoped>

.item {
  display: flex;
  flex-direction: column;
  align-items: center;
  width: 136px;
  height: 177px;
  flex-shrink: 0;
  border-radius: 10px;
}

.title {
  color: var(--NestMart-TextHeading, #253D4E);
  text-align: center;
  font-family: Quicksand;
  font-size: 16px;
  font-style: normal;
  font-weight: 700;
  line-height: 20px;
  letter-spacing: -0.006px;
}

.item2 {
  color: var(--NestMart-TextHeading, #B6B6B6);
  text-align: center;
  font-family: Lato;
  font-size: 12px;
  font-style: normal;
  font-weight: 400;
  line-height: 18px;
}

.image {
  width: 120px;
  height: 120px;
  display: flex;
  justify-content: center;
  align-items: center;
}

</style>