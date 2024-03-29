<script setup>
import { ref } from 'vue';
const props = defineProps({
  name: String
});
// Define events
const emit = defineEmits(['select']);
//
const selected = ref(false);
const select = () => {
  selected.value = true;
  emit('select', props.name)
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

