<script setup>
import {reactive, ref, watch} from "vue";
const frontend = ref("Фронтдент - ")
const counter = ref(0)
const date = ref(new Date().toLocaleTimeString());

function frontendHandler(event) {
  frontend.value += "самое сложное направление программирования"
}
function counterHandler(event) {
  console.log();
  counter.value++;
}
  watch({}, () => {
    setInterval(() => {
      date.value = new Date().toLocaleTimeString();
      }, 2000)
  }, {immediate: true})
</script>

<template>
  <div>
  <button @click="counterHandler">counter {{ counter }}</button>
    <button @mousemove.once="frontendHandler">  {{frontend}}</button>
  <h1> {{ date}}</h1>

  </div>
</template>

<style lang = "scss" scoped> </style>