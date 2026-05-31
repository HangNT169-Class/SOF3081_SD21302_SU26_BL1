<script setup>
import { ref } from 'vue'

const lists = ref([
  {
    ma: 'TH001',
    ten: 'Phong001',
    dienTich: 50,
    sucChua: 30,
    chucNang: 'abdhdjjj',
  },
  {
    ma: 'TH002',
    ten: 'Phong002',
    dienTich: 100,
    sucChua: 50,
    chucNang: 'oojaj',
  },
  {
    ma: 'TH003',
    ten: 'Phong003',
    dienTich: 70,
    sucChua: 80,
    chucNang: '1234e',
  },
])

const listMayTinh = ref([
  {
    ma: 'S001',
    ten: 'Nguyen',
    dongMay: 'asd',
    mauSac: 'do',
    gia: 10,
  },
  {
    ma: 'soo2',
    ten: 'Dang',
    dongMay: 'azus',
    mauSac: 'xanh',
    gia: 20,
  },
  {
    ma: 'S003',
    ten: 'Ha',
    dongMay: 'ace',
    mauSac: 'den',
    gia: 15,
  },
])
const isLogin = ref(false)
function changeIsLogin() {
  // if (isLogin.value == true) {
  //   isLogin.value = false
  // } else {
  //   isLogin.value = true
  // }
  isLogin.value = !isLogin.value
  // isLogin = true  => !isLogin = false
  // isLogin = false => !isLogin = true
}
const message = ref('')
</script>

<template>
  <h1>Buoi 9 - re nhanh</h1>
  <table border="1">
    <thead>
      <tr>
        <th>Ma</th>
        <th>Ten</th>
        <th>Dien tich</th>
        <th>Suc chua</th>
        <th>Chuc nang phong</th>
      </tr>
    </thead>
    <tbody>
      <template v-for="s1 in lists" :key="s1.ma">
        <tr>
          <td>{{ s1.ma }}</td>
          <td>{{ s1.ten }}</td>
          <td>{{ s1.dienTich }}</td>
          <td>{{ s1.sucChua }}</td>
          <td>{{ s1.chucNang }}</td>
        </tr>
      </template>
    </tbody>
  </table>
  <table border="1">
    <thead>
      <tr>
        <th>ma</th>
        <th>ten</th>
        <th>dongMay</th>
        <th>mauSac</th>
        <th>gia</th>
      </tr>
    </thead>
    <tbody>
      <template v-for="m1 in listMayTinh" :key="m1.ma">
        <tr>
          <td>
            {{ m1.ma }}
          </td>
          <td>{{ m1.ten }}</td>
          <td>{{ m1.dongMay }}</td>
          <td>{{ m1.mauSac }}</td>
          <td>{{ m1.gia }}</td>
        </tr>
      </template>
    </tbody>
  </table>
  <button @click="changeIsLogin">Click me</button>
  <p v-if="isLogin == true">Xin chao Admin</p>
  <p v-else>Ban chua dang nhap</p>
  <!-- Bai 3 tuong tu nhu bai 2 nhung co 3TH: v-else-if="" -->
  <!-- Bai bo sung: 
  Tao danh sach MayTinh gom cac thuoc tinh sau: 
  ma - String, ten - String, dongMay - String, mauSac - String, gia - number.
  Hien thi danh sach MayTinh len table 
  -->
  <!-- 
  Bai 1: Tao 1 danh sach PhongHoc gồm các thuộc tính sau: 
  ma - String, ten - String, dienTich - number , sucChua - number , chucNang - String
  Hiển thị danh sách Phòng Học lên: 
  1. Lên table 
  2. Lên combobox 
  3. Lên ul/li 

  Bai 2: 
  Kiem tra xem bạn đã đăng nhập hay chưa ? 
  isLogin = true => Xin chào Admin 
  isLogin = false => Ban chưa đăng nhập. 
  Bài 3: 
  Hiển thị trạng thái của người chơi. 
  trangThai = online -> click -> Hiển thị Offline 
  trangThai = offline -> click -> Hiển thị busy. 
  trangThai = busy -> click -> Hiển thị Online 
  Bài 4: 
  Dựng giao diện có 1 ô input: 
  Nhập tên: input => Khi nhập gì thì dữ liệu vừa nhập hiển thị ở dưới 
  Bài 5: 
  Dựng giao diện có 2 ô input & 4 button: 
  button 1 -> + -> Hiển thị tổng 2 số nhập ở ô input
  button 2 -> - -> Hiển thị hiệu 2 số nhập ở ô input
  button 3 -> * -> Hiển thị tích 2 số nhập ở ô input
  button 4 -> / -> Hiển thị thương 2 số nhập ở ô input
    -->
  <!-- Cap nhap gia tri input =>
     C1: onChange 
     C2: v-model
      -->
  Mess: <input type="text" v-model="message" />
  <br />
  <p>Gia tri: {{ message }}</p>
</template>

<style scoped></style>
