<script setup>
import { ref } from 'vue'
import ButtonComponent from './component/ButtonComponent.vue'
import TestComponent from './component/TestComponent.vue'
const message1 = ref('Test messs')
const number = ref(10)
const listNhanVien = ref([
  {
    ma: 'NV91',
    ten: 'Nguyen Van A',
    tuoi: 10,
  },
  {
    ma: 'NV911',
    ten: '111 Van A',
    tuoi: 110,
  },
  {
    ma: 'NV911',
    ten: 'Nguy111en Van A',
    tuoi: 101,
  },
])
// const increaseNumber = () => number.value++
function increaseNumber() {
  number.value++
}
</script>
<!-- Tao 1 ds NhanVien 
 gom cac thuoc tinh sau
 ma - String, ten - String, tuoi - number 
 Hien thi danh sachs Nhan vien 3 phan tu 
 => DS nay phai duoc viet table -> ButtonComponent
 -->
<template>
  <h1>Buoi 10 - Component</h1>
  <!-- Cach goi component 
   Ten component -> Viet hoa chu cai dau & dat theo lac da:
   ButtonComponent
   C1: Goi ten file 
   C2: viet thuong 100% co bao nhieu tu thi cach nhau boi dau - 
   -->
  <!-- <button-component />
  <TestComponent /> -->
  <!-- App & Button Component: 
   App: component cha 
   Button Component: component con
    Cha ------- Con 
    => TRUYEN GIA TRI/TRUYEN SU KIEN TU COMPONENT CHA SANG COMPONENT CON 
    KHONG THE TRUYEN THEO CHIEU NGUOC LAI
    Khi truyen sang component con => :tenBien = giaTri
    -->
  <!-- int a = 5; -->
  <!-- Ten bien -> : 
    Ten su kien -> @  -->
  <ButtonComponent :test1="message1" :a="number" :danhSach="listNhanVien" />
  <TestComponent :b="number" @suKien="increaseNumber" />
  <!-- Truyen su kien: increaseNumber tu cha -> Con  -->
  <button @click="increaseNumber">Click me</button>
  <p>Gia tri ben component cha: {{ message1 }}</p>
</template>

<style scoped></style>
