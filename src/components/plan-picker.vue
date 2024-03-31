<template>
  <div class="plans">
    <plan-picker-item 
      v-for="plan in plans" 
      :key="plan" 
      :name="plan"
      @select="selectPlan"
    />
    <p>{{  selectedPlan }}</p>
  </div>
</template>

<script setup>
  import planPickerItem from './plan-picker-item.vue';
  import {ref} from 'vue';
  const plans = ref(['El soltero', 'El curioso', 'El adicto']);
  const selectedPlan = ref(null)
  const selectPlan = (name) => {
    selectedPlan.value = name;
  }
</script>
