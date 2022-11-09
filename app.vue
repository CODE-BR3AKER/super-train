<template>
  <main class="wrapper">
    <div class="wrapper__list">
      <div v-for="(car, index) in carList" :key="index">
        <Modal :car="car" />
      </div>
      <div class="car__header car__header_btn">+ New specification</div>
    </div>
    <div class="wrapper__form">
      <CarForm :options="carList" />
    </div>
  </main>
</template>
<script setup>
import cars from 'assets/cars.json';
import { ref } from 'vue';
const carList = ref([]);
carList.value = cars;
</script>
<style>
body {
  margin: 0;
  padding: 0;
  overflow-x: hidden;
  padding-top: 5rem;
  padding-bottom: 5rem;
}
.wrapper {
  margin: 0 !important;
  padding: 0 !important;
  width: 100vw;
  height: 100vh;
  display: flex;
  justify-content: space-around;
  align-items: flex-start;
}
.wrapper__list {
  display: flex;
  flex-direction: column;
}
.wrapper__form {
  width: 45vw;
}
.car__header_btn {
  margin-top: 3rem !important;
  text-align: center;
}
</style>
