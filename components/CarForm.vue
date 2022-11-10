<template>
  <form @onsubmit="emit">
    <div v-for="(value, key) in options">
      <label>{{ key }}</label
      ><br />
      <input type="text" :value="value" />
    </div>
  </form>
</template>

<script lang="ts" setup>
import { defineProps, defineEmits } from 'vue';
import { CarInterface } from '~/types';
/* submit: (formData: { name: string; type: string }) => {
          get<BuilderInterface>('builder').buildField(formData);
        }, */
const emit = defineEmits(['submit']);
const { options } = defineProps<{
  options: CarInterface;
}>();
</script>
<style>
form {
  width: 100%;
  display: flex;
  flex-direction: column;
}
</style>
