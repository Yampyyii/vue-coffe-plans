<script setup>
import { computed } from 'vue';

const props = defineProps({
  name: String,
  selectedPlan: String
});

const isSelected = computed(() => props.selectedPlan === props.name);

// Define events
const emit = defineEmits(['select']);

const select = () => {
  emit('select', props.name)
};
</script>

<template>
  <div 
    @click="select" 
    class="plan" :class="{'selected-plan': isSelected}">
    <div class="description">
      <span class="title">
        {{name}}
      </span>
    </div>
  </div>
</template>