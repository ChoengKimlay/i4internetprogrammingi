<template>

  <div class="wrap">

    <MenuComponent title="Featured Categories"></MenuComponent>

    <div style="display: flex; justify-content: space-between;">
      <div v-for="i in Category">
        <CategoryComponent :Color="i.color" :Img="i.img" :Title="i.title" :Item="i.item"></CategoryComponent>
      </div>
    </div>

    <div style="display: flex; justify-content: space-between;">
      <div v-for="i in Promotion">
        <PromotionComponent :Text="i.text" :Img="i.img" :Color="i.color" :Btn="i.btn" :TextBtn="i.txtbtn"></PromotionComponent>
      </div>
    </div>

   <MenuComponent title="Popular Products"></MenuComponent>

    <div style="display: flex; justify-content: space-between; flex-wrap: wrap; gap: 20px;">
      <div v-for="i in Products">
        <ProductComponent :tag="i.tag" :tagBg="i.tagBg" :image="i.image" :name="i.name" :rate="i.rate" :sellPrice="i.sellPrice" :discountPrice="i.discountPrice"></ProductComponent>
      </div>
    </div>

  </div>

</template>

<script>
import ButtonComponent from './components/ButtonComponent.vue';
import PromotionComponent from './components/PromotionComponent.vue';
import CategoryComponent from './components/CategoryComponent.vue';
import MenuComponent from "./components/MenuComponent.vue";
import ProductComponent from './components/ProductComponent.vue';
import { useTodoStore } from "./stores/todo";
import { mapState } from 'pinia';

export default {
  name: "App",
  components: {
    ButtonComponent,
    PromotionComponent,
    CategoryComponent,
    MenuComponent,
    PromotionComponent,
    ProductComponent
},
  setup() {
    const todoStore = useTodoStore();
    return { todoStore };
  },
  computed: {
    ...mapState(useTodoStore, ["Promotion"]),
    ...mapState(useTodoStore, ["Category"]),
    ...mapState(useTodoStore, ["Products"]),
  }

}
</script>

<style scoped>

.wrap {
  display: flex;
  flex-direction: column;
}

*{
  overflow-x: hidden;
}

</style>