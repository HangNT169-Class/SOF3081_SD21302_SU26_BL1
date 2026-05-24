<!-- Single-File Components: .vue
  chua code logic - JS , giao dien - html, lam dep - css -->
<!-- Day la code JS - luon luon phai co setup -->
<script setup>
const test = 'Test gia tri SOF308'
const button1 = '<button type="button" class="btn btn-primary">Primary</button>'
const valueClass = 'class-test'

// function bt hoac arrow function
function test2() {
  console.log('Test aaaa')
}
const test1 = () => {
  console.log('Arrrow function test aaa')
}
</script>
<!-- Giao dien - html => template -->
<template>
  <h1>Buoi 6 - Lam quen voi VueJS</h1>
  <!-- {{ gia tri }} - hien thi gia tri len giao dien -->
  <p>{{ test }}</p>
  <!-- {{  }} => hien thi dung gia tri cua bien duoc truyen -->
  <div>{{ button1 }}</div>
  <!-- Muon dinh dang html => v-html -->
  <div v-html="button1"></div>
  <!-- Binding du lieu: 
   Gan id/class - bind 
   C1: v-bind:id/class ="ten bien"
   C2: :id/:class="ten bien"
    -->
  <p :class="valueClass">aaaaa</p>
  <!-- Event su kien: 
   C1: v-on:tensk="ten ham"
   C2: @sk = "ten ham" VD: @change="aaa", @click=""
    -->
  <button v-on:click="test2()">Click 1</button>
  <button @click="test1()">Click 2</button>
</template>
<!-- Code lam dep -->
<style>
h1 {
  text-align: center;
  color: red;
}
</style>
