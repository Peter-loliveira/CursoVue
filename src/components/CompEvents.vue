<template>
  <div>
    <h1 class="titulos">Eventos</h1>
    <h2>Formulário</h2>
    <form action="https://www.google.com.br" @submit.prevent="submeter">
      <input type="text" @keypress.enter="submeter" />
      <br />
      <button type="submit">Enviar</button>
    </form>
  </div>
  <hr />
</template>

<script>
export default {
  name: "CompEvents",
  data() {},
  methods: {
    submeter: (event) => {
      alert("Formulário Enviado");
      console.log(event);
    },
  },
};
</script>

<style></style>
