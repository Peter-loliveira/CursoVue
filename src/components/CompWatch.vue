<template>
  <div>
    <h1 class="titulos">Watch</h1>
    <input type="text" v-model="nameWatch" />
    <h2>{{ nameWatch }}</h2>

    <select v-model="pageCount">
      <option value="5">5</option>
      <option value="10">10</option>
      <option value="15">15</option>
    </select>
    <br />
    <br />
    <label>{{ pageCount }}</label>
  </div>
  <hr />
</template>

<script>
export default {
  name: "CompWatch",
  data() {
    return {
        pageCount: 5,
        nameWatch: '',
    };
  },
  methods: {
    saveName: (nome) => {
        if (nome.length >= 5) {
            alert(`O nome ${nome} tem ${nome.length} caracteres`)
        }
    },
    changePage(value){
        alert(`${value} páginas selecionadas!`)
    },
  },
  watch: {
    nameWatch(newValue){
        this.saveName(newValue)
    },
    pageCount(){
        this.changePage(this.pageCount)
    }
  }
};
</script>

<style></style>
