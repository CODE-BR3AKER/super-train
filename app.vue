<template>
  <main class="wrapper">
    <div class="wrapper__list">
      <div v-for="(car, index) in carList" :key="index">
        <Modal :car="car" @update="changeCar(value)" />
      </div>
      <div class="car__header car__header_btn">+ New specification</div>
    </div>
    <div class="wrapper__form">
      <CarForm :options="currentCar" />
    </div>
  </main>
</template>
<script setup>
import cars from 'assets/cars.json';
import { ref } from 'vue';
const carList = ref([]);
carList.value = cars;
const currentCar = ref({
  name: '',
  engine: '',
  interior_material: '',
  color: '',
  wheel_rims: '',
  type_of_wheels: '',
  signature: '',
});
function changeCar(c) {
  currentCar.value.name = c.name;
  currentCar.value.engine = c.engine;
  currentCar.value.interior_material = c.interior_material;
  currentCar.value.color = c.color;
  currentCar.value.wheel_rims = c.wheel_rims;
  currentCar.value.type_of_wheels = c.type_of_wheels;
  currentCar.value.signature = c.signature;
}
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
