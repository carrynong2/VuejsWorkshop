<template>
  <section>
    <img :src="picture" :width="size" :height="size" />
    <h1>ชื่อ-นามสกุล : {{ getFullName() }}</h1>
    <h1>อายุ : {{ age }} ปี</h1>
    <p>ที่อยู่ : <span v-html="address"></span></p>
    <a :href="social" target="_blank">Facebook</a>
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
