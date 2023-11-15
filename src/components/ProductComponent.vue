<template>
  
  <div class="wrap">

    <div class="discount" :style="{background: tagBg}">{{ tag }}</div>
    <img :src=image class="img" alt="">

    <div class="info">
      <div class="item">Hodo Foods</div>
      <div class="title">{{ name }}</div>

      <div class="rating">
        <span v-for="i in 5">
          <img src="../assets/star-yellow.svg" v-if="i <= rate" alt="">
          <img src="../assets/star-white.svg" v-else alt="">
        </span>
        <span>{{ rate }}</span>
      </div>

      <div class="gram">{{ description }}</div>

      <div class="price">
        <div class="price_info">
          <span>${{ sellPrice }}</span>
          <del class="sellDis">${{ discountPrice }}</del>
        </div>
        <div @click="increaseNum()" v-if="button == true">
          <AddButtonComponent/>
        </div>
        <div @click="decreaseNum()" v-else>
          <AddComponent/>
        </div>
      </div>

    </div>

  </div>

</template>

<script>

import AddComponent from './AddComponent.vue';
import AddButtonComponent from './AddButtonComponent.vue';
export default {
  name: "ProductComponent",
  components: {
    AddButtonComponent,
    AddComponent
},
  methods: {
    increaseNum() {
      this.button = false;
    },
    decreaseNum() {
      let n = document.getElementById("input_number");
      if (n.value == 0) {
        this.button = true;
      }
    }
  },
  props: {
    tag: String,
    tagBg: String,
    image: String,
    name: String,
    rate: Number,
    description: String,
    sellPrice: String,
    discountPrice: String,
  },
  data() {
    return {
      button: true,
    }
  }
}

</script>

<style scoped>

@import url("https://fonts.googleapis.com/css2?family=Lato:wght@300&family=Quicksand:wght@500&display=swap");

.wrap {
  width: 280px;
  height: 400px;
  border-radius: 10px;
  border: 1px solid #bce3c9;
  background: #fff;
  position: relative;
}

.wrap:hover {
  transform: scale(90%);
}

.discount {
  width: 58px;
  height: 32px;
  display: flex;
  justify-content: center;
  align-items: center;
  gap: 10px;
  position: absolute;
  left: 0;
  top: 20px;
  border-radius: 0px 30px 30px 0px;
  color: #fff;
  font-family: Lato;
  font-size: 12px;
}

.img {
  position: absolute;
  width: 200px;
  top: 60px;
  left: 50%;
  translate: -50% 0;
  mix-blend-mode: multiply;
}

.info {
  width: 261px;
  position: absolute;
  bottom: 0;
  left: 50%;
  translate: -50% 0;
  padding-bottom: 20px;
}

.info > div {
  margin-top: 3px;
}

.item {
  color: var(--NestMart-TextBody, #7e7e7e);
  font-family: Lato;
  font-size: 14px;
  font-style: normal;
  font-weight: 400;
  line-height: 18px;
}

.title {
  color: var(--NestMart-TextHeading, #253d4e);
  font-family: Quicksand;
  font-size: 15px;
  font-style: normal;
  font-weight: 700;
}

.rating {
  font-family: Lato;
  font-size: 14px;
}
.rating img {
  margin-right: 5px;
}

.gram {
  color: var(--NestMart-TextBody, #7e7e7e);
  font-family: Lato;
  font-size: 12px;
}

.price {
  width: 260px;
  height: 32px;
  display: flex;
  align-items: center;
  justify-content: space-between;
}

.price_info {
  color: var(--NestMart-Brand-1, #3bb77e);
  font-family: Quicksand;
  font-size: 20px;
  font-style: normal;
}

.sellDis {
  color: var(--NestMart-TextBody, #7e7e7e);
  font-family: Quicksand;
  font-size: 12px;
  margin-left: 5px;
}

</style>