<template>
  <div>
    <h1 class="titulos">V-Model</h1>
    <input type="text" v-model="nameModel" />
    <br />
    <label> {{ nameModel }}</label>
    <br />

    <select v-model="selecao">
      <option value="Selecione uma Opção">Selecione uma Opção</option>
      <option value="Opção 1">Opção 1</option>
      <option value="Opção 2">Opção 2</option>
      <option value="Opção 3">Opção 3</option>
      <option value="Opção 4">Opção 4</option>
      <option value="Opção 5">Opção 5</option>
    </select>

    <input type="text" v-model="selecao" />
    <br />
    <ul>
      <li>
        <input type="checkbox" v-model="colors" value="Amarelo" />
        Amarelo
      </li>
      <li>
        <input type="checkbox" v-model="colors" value="Vermelho" />
        Vermelho
      </li>
      <li>
        <input type="checkbox" v-model="colors" value="Azul" />
        Azul
      </li>
      <li>
        <input type="checkbox" v-model="colors" value="Verde" />
        Verde
      </li>
      <li>
        <input type="checkbox" v-model="colors" value="Preto" />
        Preto
      </li>
      <li>
        <input type="checkbox" v-model="colors" value="Branco" />
        Branco
      </li>
    </ul>
    <h4>Cores Selecionadas</h4>
    <input type="text" class="coresSelecionadas" :value="colors" />
    <hr />
  </div>
</template>

<script>
export default {
  name: "CompVmodel",
  data() {
    return {
      nameModel: "",
      selecao: "",
      colors: [],
    };
  },

  methods: {},

  computed: {},
};
</script>

<style>
.coresSelecionadas {
  width: 50%;
}
</style>
