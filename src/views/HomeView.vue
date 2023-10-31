<template>
  <div id="app">
    <h1>Kalkulator Vue</h1>
    <input v-model="angka1" type="text" placeholder="Masukkan angka pertama" />
    <input v-model="angka2" type="text" placeholder="Masukkan angka kedua" />
    <button @click="hitung('+')">+</button>
    <button @click="hitung('-')">-</button>
    <button @click="hitung('*')">*</button>
    <button @click="hitung('/')">/</button>
    <p>Hasil: {{ hasil }}</p>
  </div>
</template>


<script>
export default {
  data() {
    return {
      angka1: "",
      angka2: "",
      hasil: "",
    };
  },
  methods: {
    hitung(operator) {
      if (this.angka1 !== "" && this.angka2 !== "") {
        const num1 = parseFloat(this.angka1);
        const num2 = parseFloat(this.angka2);

        if (operator === '+') {
          this.hasil = num1 + num2;
        } else if (operator === '-') {
          this.hasil = num1 - num2;
        } else if (operator === '*') {
          this.hasil = num1 * num2;
        } else if (operator === '/') {
          if (num2 !== 0) {
            this.hasil = num1 / num2;
          } else {
            this.hasil = "Tidak dapat membagi dengan nol";
          }
        }
      }
    },
  },
};
</script>
