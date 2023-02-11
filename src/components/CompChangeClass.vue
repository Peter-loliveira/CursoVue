<template>
  <div>
    <button v-on:click="changeClass()">Mudar Classe</button>
    <h1 :class="{ 'title-home': isHome }">Classe dinâmica</h1>
    <p :class="{ 'title-home': isHome }">
      Mussum Ipsum, cacilds vidis litro abertis. Per aumento de cachacis, eu
      reclamis. Todo mundo vê os porris que eu tomo, mas ninguém vê os tombis
      que eu levo! Suco de cevadiss deixa as pessoas mais interessantis. Admodum
      accumsan disputationi eu sit. Vide electram sadipscing et per. Mé faiz
      elementum girarzis, nisi eros vermeio. Si u mundo tá muito paradis? Toma
      um mé que o mundo vai girarzis! Nec orci ornare consequat. Praesent
      lacinia ultrices consectetur. Sed non ipsum felis. Vehicula non. Ut sed ex
      eros. Vivamus sit amet nibh non tellus tristique interdum.
    </p>
    <hr />
  </div>
</template>

<script>
export default {
  name: "CompChangeClass",
  data() {
    return {
      isHome: false,
    };
  },
  methods: {
    changeClass: function () {
      this.isHome = !this.isHome;
    },
  },
};
</script>

<style>
.title {
  color: blue;
  font-size: 20px;
}
.title-home {
  color: green;
  font-size: 30px;
}

button {
  font-size: 15px;
  font-weight: bold;
  color: #fff;
  background-color: red;
  border-color: #fff;
  padding: 5px 10px;
  border-radius: 20px;
  width: 150px;
  height: 40px;
}

button:hover {
  background-color: black;
}
</style>
