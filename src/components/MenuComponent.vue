<template>

<link href="https://fonts.googleapis.com/css2?family=Quicksand:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Lato:wght@300;400;700&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Montserrat:wght@300;400;500;600;700&display=swap" rel="stylesheet">

  <div class="Menu">
    <div class="Title">{{ title }}</div>
    <div class="Option">
      <div class="All">All</div>
      <div class="Right">Milks & Dairies</div>
      <div class="Right">Coffees & Teas</div>
      <div class="Right">Pet Foods</div>
      <div class="Right">Meats</div>
      <div class="Right">Vegtables</div>
      <div class="Right">Fruits</div>
    </div>
  </div>

</template>

<script>

export default {
  name: "Menu",
  props: {
    title: String,
  }
}

</script>

<style>

.Menu {
  display: flex;
  justify-content: space-between;
  margin: 20px 20px 40px;
}

.Title {
  color: var(--NestMart-TextHeading, #253D4E);
  font-family: Quicksand;
  font-size: 32px;
  font-style: normal;
  font-weight: 700;
}

.Option {
  display: flex;
  align-items: center;
}

.All {
  color: var(--NestMart-TextHeading, #253D4E);
  font-family: Montserrat;
  font-style: normal;
  font-weight: 700;
}

.Right {
  color: var(--NestMart-TextHeading, #253D4E);
  margin-left: 30px;
  font-family: Lato;
  font-style: normal;
  font-weight: 400;
}
</style>