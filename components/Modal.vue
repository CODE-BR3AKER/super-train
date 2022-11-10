<template>
  <div class="car">
    <div @click="toggleModal" class="car__header">
      {{ car.name }}
    </div>
    <div v-if="open" class="car__details">
      <ul>
        <li v-for="(value, key) in car">{{ key }} - {{ value }}</li>
      </ul>
    </div>
  </div>
</template>
<script setup lang="ts">
import { defineProps, ref, defineEmits } from 'vue';
import { CarInterface } from '~/types';
const open = ref(false);
const emit = defineEmits(['update:modelValue']);
function toggleModal(event: Event) {
  open.value ? (open.value = false) : (open.value = true);
  emit('update:modelValue', event.target);
}
const { car } = defineProps<{
  car: CarInterface;
}>();
</script>
<style>
.car {
  width: 45vw;
  text-align: center;
}
.car__header {
  width: 100%;
  background: #dddddd;
  padding: 2px 10px;
  margin: 10px auto;
  color: #555555;
  border: 2px solid #c4c4c4;
  border-radius: 5px;
}
.car__details {
  width: 100%;
  border: 2px dashed #c4c4c4;
  padding: 2px 10px;
}
.car__details ul {
  list-style: none;
}
.car__details ul li {
  line-height: 1.125;
}
</style>
