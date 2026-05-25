<script setup>
import { ref } from 'vue'

// let count = 0
// VueJS => khai bao bien binh thuong => gia tri co thay doi
// nhung k cap nhap vao dom
// Xu ly:
// C1: Khai bao bien bang ref
// C2: Khai bao bien bang reactive
let count = ref(0)
function clickMe() {
  // count++
  // Voi bien ref => tenBien.value
  // count.value++
  // count.value = count.value +1
  console.log(count.value)
  // alert('Ban da click vao day')
}
// Tao 3 button: button +, button -, button reset
// Neu click vao button + => gia tri tang 2 don vi
// Neu click vao button - => gia tri giam 3 don vi
// Neu click vao button reset => gia tri chuyen thanh 0
let count1 = ref(0)
function tang() {
  if (count1.value >= 15) {
    alert('Toi da')
  } else {
    count1.value += 2
  }
}
function giam() {
  if (count1.value <= -20) {
    alert('Toi thieu')
  } else {
    count1.value -= 3
  }
}
function reset() {
  count1.value = 0
}
// Bo sung vao bai 1 dieu kien:
// Neu click gia tri >=15 thi hien thi thong bao. Đã tới giới hạn rồi
// Neu click gia tri <=-20 thi hien thi thong bao. Đã tới tối thiểu rồi
/**
 * 2. Tao 1 đối tượng SinhVien gồm các thuộc tính: mssv - String, ten - String, tuoi - number
 * Fix cứng 1 đối tượng SinhVien va hien thị thông tin lên giao diện
 * 3. Tạo 1 mảng số nguyên gồm 10 phần tử - fix cứng.
 * Hiện thị giá trị của phần tử ở vị trí cuối cùng
 * 4. Tạo 1 mảng đối tượng GiangVien gồm các thuộc tính:
 * maGV - String, ten-String, bac - number, tuoi - number, chuyenNganh - String
 * Hien thị danh sách mảng đối tượng Giảng Viên theo các cách dưới đây:
 *    4.1. Hiển thị dưới dạng table
 *    4.2. Hiển thị dưới dạng combobox
 *    4.3. Hiển thị dưới dạng ul,li
 */
// reactive : doc them
// Khoi tao 1 bien ref voi kieu Object => {}
const sinhVien = ref({
  mssv: 'SV01',
  ten: 'Nguyen Van A',
  tuoi: 10,
})
// Khoi tao 1 bien ref voi kieu mang => []
const mangSoNguyen = ref([9, -10, 11, 3, 4, 5, 7, 8, 0, 51])
// Khoi tao 1 bien ref voi kieu mang object => [{},{}]
const listGiangVien = ref([
  {
    maGV: 'GV01',
    ten: 'Nguyen Van A',
    bac: 4,
    tuoi: 10,
    chuyenNganh: 'Xu ly du lieu',
  },
  {
    maGV: 'GV02',
    ten: 'Nguyen Van B',
    bac: 5,
    tuoi: 16,
    chuyenNganh: 'Phat trien pham mem',
  },
  {
    maGV: 'GV03',
    ten: 'Nguyen Van C',
    bac: 10,
    tuoi: 20,
    chuyenNganh: 'Ung dung phan mem',
  },
])
</script>
<template>
  <h1>Buoi 7 - Ref & Reactive & Vong lap</h1>
  <div>
    <p>Gia tri count = {{ count }}</p>
    <button @click="clickMe">Click</button>
  </div>
  <div>
    <h1>Luyen tap 1</h1>
    <p>Gia tri: {{ count1 }}</p>
    <button @click="tang">+</button>
    <button @click="giam">-</button>
    <button @click="reset">reset</button>
  </div>
  <div>
    <p>MSSV: {{ sinhVien.mssv }}</p>
    <p>Ten: {{ sinhVien.ten }}</p>
    <p>Tuoi: {{ sinhVien.tuoi }}</p>
    <p>Gia tri phan tu o vi tri cuoi: {{ mangSoNguyen[9] }}</p>
  </div>
  <div>
    <h1>Mang Object V-For</h1>
    <!-- Cu phap vong lap VueJS: v-for
     v-for = (value,key,index) in ds mang : key = keyTruyenVao
     Key truyen vao => Khoa chinh
     (1ths) => ths => value  
      -->
    <h1>Hien thi duoi table</h1>
    <table border="1">
      <thead>
        <tr>
          <th>STT</th>
          <th>Ma</th>
          <th>Ten</th>
          <th>Tuoi</th>
          <th>Bac</th>
          <th>Chuyen nganh</th>
        </tr>
      </thead>
      <tbody>
        <template v-for="(s, i) in listGiangVien" :key="s.maGV">
          <tr>
            <td>{{ i + 1 }}</td>
            <td>{{ s.maGV }}</td>
            <td>{{ s.ten }}</td>
            <td>{{ s.tuoi }}</td>
            <td>{{ s.bac }}</td>
            <td>{{ s.chuyenNganh }}</td>
          </tr>
        </template>
      </tbody>
    </table>
    <!-- Hien thi duoi combobox & ul/li -->
  </div>
  <div>
    <h1>Nhung booostrap</h1>
    <button type="button" class="btn btn-outline-primary">Primary</button>
    <button type="button" class="btn btn-outline-secondary">Secondary</button>
    <button type="button" class="btn btn-outline-success">Success</button>
    <button type="button" class="btn btn-outline-danger">Danger</button>
    <button type="button" class="btn btn-outline-warning">Warning</button>
    <button type="button" class="btn btn-outline-info">Info</button>
    <button type="button" class="btn btn-outline-light">Light</button>
    <button type="button" class="btn btn-outline-dark">Dark</button>
  </div>
</template>

<style scoped></style>
