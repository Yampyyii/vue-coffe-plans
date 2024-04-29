<template>
    <div class="plans">
      <plan-item v-for="plan in plans" :key="plan" :name="plan" />
    </div>
  </template>
  
  <script setup>
    import planItem from './plan-picker-item.vue';
    import {ref} from 'vue';
    const plans = ref(['El soltero', 'El curioso', 'El adicto']);
  </script>
  