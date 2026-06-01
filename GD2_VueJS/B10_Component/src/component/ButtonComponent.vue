<!-- 1 component -> .vue gom 3 thanh phan -->
<script setup>
// Can lay gia tri ben component cha -> con: defineProps
const giaTriTruyen = defineProps({
  test1: String,
  a: Number,
  danhSach: Array,
})
</script>
<template>
  <h1>Button Component Test</h1>
  <p>Gia tri duoc truyen sang component con: {{ giaTriTruyen.test1 }}</p>
  <p>Gia tri duoc truyen sang component con: {{ giaTriTruyen.a }}</p>
  <table border="1" cellpadding="10" cellspacing="0">
    <thead>
      <tr>
        <th>Ma</th>
        <th>Ten</th>
        <th>Tuoi</th>
      </tr>
    </thead>
    <tbody>
      <template v-for="value in giaTriTruyen.danhSach" :key="value.ma">
        <tr>
          <td>{{ value.ma }}</td>
          <td>{{ value.ten }}</td>
          <td>{{ value.tuoi }}</td>
        </tr>
      </template>
    </tbody>
  </table>
</template>

<style>
h1 {
  text-align: center;
}
</style>
