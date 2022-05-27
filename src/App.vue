<template>
  <section>
    <h1>ชื่อ-นามสกุล : {{ getFullName() }}</h1>
    <h1>อายุ : {{ age }} ปี</h1>
    <p>ที่อยู่ : <span v-html="address"></span></p>
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
