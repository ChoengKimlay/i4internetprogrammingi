<template>

  <div class="promotion" :style="{backgroundColor: Color}">
    <div class="quote">
      <div class="text">{{ Text }}</div>
    </div>
    <div class="img">
      <img :src=Img alt="">
    </div>
    <ButtonComponent :text="TextBtn" :color="Btn" class="btn"></ButtonComponent>
  </div>

</template>

<script>

import ButtonComponent from './ButtonComponent.vue';
export default {
  name: "Promotion",
  props: {
    Text: String,
    Img: String,
    TextBtn: String,
    Btn: String,
    Color: String,
  },
  components: {
    ButtonComponent
  }
}

</script>

<style scoped>

.promotion {
  margin: 40px 0px 20px 0;
  width: 490px;
  height: 300px;
  position: relative;
  border-radius: 10px;
}

.promotion:hover {
  transform: scale(90%);
}

.img {
  position: absolute;
  display: flex;
  justify-content: end;
  align-items: end;
  width: 200px;
  height: 250px;
  right: 0px;
  bottom: 0px;
}

.quote {
  position: absolute;
  width: calc(512px-200px);
  position: relative;
}

.text{
  position: relative;
  top: 75px;
  left: 48px;
  width: 270px;
  color: var(--NestMart-TextHeading, #253d4e);
  font-family: Quicksand;
  font-size: 28px;
  font-style: normal;
  font-weight: 700;
  z-index: 10;
}

.btn {
  position: absolute;
  left: 48px;
  bottom: 75px;
}

img {
  height:200px;
  border-radius: 20px;
}

</style>