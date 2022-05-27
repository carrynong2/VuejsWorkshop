<template>
  <section>
    <img :src="picture" :width="size" :height="size" />
    <h1>ชื่อ-นามสกุล : {{ getFullName() }}</h1>
    <h1>อายุ : {{ age }} ปี</h1>
    <p>ที่อยู่ : <span v-html="address"></span></p>
    <p>Social : <a :href="social" target="_blank">Facebook</a></p>
    <p>งานอดิเรก:</p>
    <ul>
      <li>{{ hobby[0] }}</li>
      <li>{{ hobby[1] }}</li>
      <li>{{ hobby[2] }}</li>
    </ul>
    <p>ข้อมูลพื้นฐาน :</p>
    <ul>
      <li>เพศ: {{ general.gender }}</li>
      <li>น้ำหนัก: {{ general.weight }} kg</li>
      <li>ส่วนสูง: {{ general.height }} cm</li>
      <li>โรคประจำตัว: {{ general.status }}</li>
    </ul>
    <button @click="showData">คลิกเพื่อดูข้อมูล</button>
    <button @click="increment(10)">เพิ่ม</button>
    <button @click="decrement(5)">ลด</button>
  </section>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      firstName: "Dev",
      lastName: "CarryNong",
      age: 25,
      address: "<i>กรุงเทพมหานคร</i>",
      picture: "https://cdn-icons-png.flaticon.com/512/6970/6970635.png",
      size: 150,
      social: "https://www.facebook.com/monthon.mukkun/",
      hobby: ["ทำสวน", "เล่นเกม", "ฟังเพลง"],
      general: { gender: "ชาย", weight: 70.4, height: 170, status: false },
    };
  },
  methods: {
    getFullName() {
      return `${this.firstName}  ${this.lastName}`;
    },
    showData() {
      alert(this.firstName);
    },
    increment(value) {
      this.age += value;
    },
    decrement(value) {
      this.age -= value;
    },
  },
};
</script>

<style></style>
