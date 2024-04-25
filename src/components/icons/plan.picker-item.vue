<template>
    <div
   @click="select"
   :class="{'selected-plan':selected}" 
   class="plan">
    <div class="desciption">
      <span class="title">
        {{name}} {{ selected ? "🍻" : ""}}
      </span>
    </div>
  </div>
</template>

<script setup>
import { ref } from 'vue';
const selected = ref (false);
const select =() => {
    selected.value = true
} 
defineProps({
    name: {
        type: String,
        requires: true,
    }
})
</script>

<style scoped>
  .select-plan{
    background-color: red;
  }
</style>