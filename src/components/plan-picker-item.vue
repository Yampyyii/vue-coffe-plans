<script setup>
import { ref } from 'vue';
defineProps({
  name: String
});
//
const selected = ref(false);
const select = () => {
  selected.value = true;
};
</script>

<template>
  <div 
    @click="select" 
    class="plan" :class="{'selected-plan': selected}">
    <div class="description">
      <span class="title">
        {{name}} {{ selected ? '👍' : '' }}
      </span>
    </div>
  </div>
</template>

