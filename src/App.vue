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
    };
  },
  methods: {
    getFullName() {
      return `${this.firstName}  ${this.lastName}`;
    },
  },
};
</script>

<style></style>
