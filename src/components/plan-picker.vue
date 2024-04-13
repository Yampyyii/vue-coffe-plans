<template>
  <div class="plans">
    {{ counter }}
    <plan-picker-item 
      v-for="plan in plans" 
      :key="plan" 
      :name="plan"
      @select="selectPlan"
      :selected-plan="selectedPlan"
    />
  </div>
</template>

<script setup>
  import planPickerItem from './plan-picker-item.vue';
  import {ref, onUnmounted} from 'vue';
  const plans = ref(['El soltero', 'El curioso', 'El adicto']);
  const selectedPlan = ref(null)
  const selectPlan = (name) => {
    selectedPlan.value = name;
  }
  onUnmounted(() => {
    console.log('Plan picker unmounted...')
    clearInterval(interval)
  })

  // Creando contador automático
  const counter = ref(0);
  const interval = setInterval(() => {
    console.log("Counter working...")
    counter.value++;
  }, 1000);
</script>
