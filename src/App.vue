<script setup>
  import planPicker from './components/plan-picker.vue';
  import {ref} from 'vue';
  const show = ref(true);
</script>

<template>
  <header>
    <div>
      <span id="logo">Liquid Gold Box</span>
      <img src="./assets/logo.png" alt="logo">
    </div>
  </header>

  <div class="content">
    <h1 class="title">Coffee Plans</h1>

    <h2 class="subtitle">
      Viajamos por el mundo para encontrar el mejor café de origen único para ti
    </h2>

    <label for="">
      <input type="checkbox" v-model="show"> Mostrar selector de planes
    </label>
    <plan-picker v-if="show"/>
    
  </div>
</template>

<style scoped>
</style>
