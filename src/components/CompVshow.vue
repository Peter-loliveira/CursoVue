<template>
  <div>
    <h1 class="titulos">v-show</h1>
    Nome: 
    <input type="text" v-model = "user.firstName">
    <br>
    Sobrenome: 
    <input type="text" v-model = "user.lastName">
    <br>
    Nome Completo: {{  this.user.firstName  }} {{ this.user.lastName }}
    <hr />
  </div>
</template>

<script>
export default {
  name: "ComVshow",
  data() {
    return {
      user: {
        firstName: "Peter",
        lastName: "Lange",
      },
    };
  },
};
</script>

<style>

</style>
