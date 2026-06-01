<template>
  <h1>Test component</h1>
  <p>Gia tri con:{{ a.b }}</p>
  <button @click="clickCon">Click con</button>
</template>
<script setup>
// function increaseNumber() {
//   a.b++
// }
const a = defineProps({
  b: Number,
})
// Truyen su kien: defineEmits
// 1 file -> 1 defineProps
// N -> defineEmits
const eventCon = defineEmits('suKien')
// const eventCon1 = defineEmits('test')
function clickCon() {
  eventCon('suKien') // Day moi la cach goi ham cha
}
</script>
