<template>
  <section>
    <img :src="picture" :width="size" :height="size" ref="imageEl" /><br />

    <h1>ชื่อ-นามสกุล : {{ getFullName }}</h1>
    <h1>อายุ : {{ age }} ปี</h1>
    <h1>เงินเดือน : {{ salary }} บาท</h1>
    <h1>ตำแหน่งงาน : {{ getDepartment }}</h1>
    <button @click="addSalary(5000)">เพิ่มเงินเดือน</button>
    <button @click="toggleVisible">
      {{ isVisible ? "ซ่อน" : "แสดง" }}รายละเอียด
    </button>
    <article v-show="isVisible">
      <p>ที่อยู่ : <span v-html="address"></span></p>
      <p>Social : <a :href="social" target="_blank">Facebook</a></p>
      <p v-if="hobby.length === 0">ไม่มีงานอดิเรก</p>
      <div v-else>
        <p>งานอดิเรก:</p>
        <ul>
          <li v-for="(item, index) in hobby" :key="index">{{ item }}</li>
        </ul>
      </div>
      <p>ข้อมูลพื้นฐาน :</p>
      <ul>
        <li v-for="(item, key) in general" :key="key">{{ item }}</li>
      </ul>
    </article>
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
      hobby: [
        "ทำสวน",
        "เล่นเกม",
        "ทำอาหาร",
        "ดูทีวี",
        "ท่องเน็ต",
        "อ่านหนังสือ",
        "เลี้ยงแมว",
      ],
      general: { gender: "ชาย", weight: 70.4, height: 170, status: false },
      isVisible: false,
      salary: 10000,
    };
  },
  methods: {
    toggleVisible() {
      this.isVisible = !this.isVisible;
    },
    addSalary(value) {
      this.salary += value;
    },
  },
  computed: {
    getFullName() {
      return `${this.firstName}  ${this.lastName}`;
    },
    getIncome() {
      return this.salary * 12;
    },
    getDepartment() {
      return this.salary >= 35000 ? "Project manager" : "Programmer";
    },
  },
  watch: {
    salary(value) {
      if (value > 50000) {
        alert("เงินเดือนไม่ควรเกิน 50,000 บาท");
        setTimeout(() => {
          this.salary = 50000;
        }, 2000);
      }
    },
  },
};
</script>

<style></style>
