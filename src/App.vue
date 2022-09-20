<script>
import axios from "axios";
export default {
  data() {
    return {
      cep: "",
      endereco: {},
    };
  },
  methods: {
    async buscar() {
      const url = `https://viacep.com.br/ws/${this.cep}/json/`;
      const { data } = await axios.get(url);
      this. endereco = data;
    },
  },
};
</script>

<template>
  <header>
    <h1>Buscar CEP</h1>
    <form @submit.prevent="buscar">
      <input type="text" v-model="cep" placeholder="Digite o CPF" />
      <button type="submit">Buscar</button>
    </form>
  </header>
</template>

<style scoped>
header {
  height: 300px;
  width: 400px;
  background-color: rgb(60, 212, 223);
}
</style>
