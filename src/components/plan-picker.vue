<template>
  <div ref="plansWrapper" 
 class="plans">
    <plan-picker-item
    @select="printSelected"
    :selectedPlan="selectedPlan"
    v-for="plan in plans" 
    :name="plan"
    v-bind:key="plan" />

    <p style="font-size: 30px;">Counter:{{ counter }}</p>
  </div>
</template>

<script setup>
import { ref, onMounted, onUnmounted} from 'vue';
import planPickerItem from './plan-picker-item.vue';
const plans = ref([
"El soltero",
"El adicto",
"El viajero",
]);
const plansWrapper =ref(null);
const selectedPlan = ref(null);

const printSelected = (playload) => {
  selectedPlan.value = playload;
}
//Crerando una referencua reactiva.
//para un contador
const counter = ref(0);
//creando un metodo para incrementar un contadoe
const processId = setInterval(()=>{
  console.log('Incrementando contador')
counter.value++;
},1000);


 //Registrando el CB (Call Back) onMounted
 onMounted(()=>{
//obteniendo la referencia del elemento .plans
 console.log('Componenten Plan Picker montado');
 });
 //registrando el CB de OnMounted
onUnmounted(()=>{
//obteniendo la referencia del elemento .plans
 console.log('Componente Plan Picker desmontado');
 clearInterval(processId);
 });
</script>