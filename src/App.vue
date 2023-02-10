<template>
  <TheHeader v-if="showHeader" />
  <CompVshow />
  <CompVbind />
  <CompVmodel />
  <CompWatch />
  <CompEvents />
  <CompPropsComputeds />
  <CompCondicionais />

  <div>
    <h1 class="titulos">v-for</h1>
    <select>
      <option id="firstItem">Selecione uma CICOM</option>
      <option v-for="cicom in cicoms" v-bind:key="cicom.index">
        {{ cicom.cicom }} - {{ cicom.circuito }}
      </option>
    </select>
  </div>
  <hr />

  <div>
    <button @click="changeClass">Mudar Classe</button>
    <h1 :class="{ title: true, 'title-home': isHome }">Classe dinâmica</h1>

    <p :class="['title', { 'title-home': isHome }]">
      Mussum Ipsum, cacilds vidis litro abertis. Per aumento de cachacis, eu
      reclamis. Todo mundo vê os porris que eu tomo, mas ninguém vê os tombis
      que eu levo! Suco de cevadiss deixa as pessoas mais interessantis. Admodum
      accumsan disputationi eu sit. Vide electram sadipscing et per. Mé faiz
      elementum girarzis, nisi eros vermeio. Si u mundo tá muito paradis? Toma
      um mé que o mundo vai girarzis! Nec orci ornare consequat. Praesent
      lacinia ultrices consectetur. Sed non ipsum felis. Vehicula non. Ut sed ex
      eros. Vivamus sit amet nibh non tellus tristique interdum.
    </p>
  </div>
  <hr />
</template>

<script>
import TheHeader from "./components/TheHeader.vue";
import CompVbind from "./components/CompVbind.vue";
import CompWatch from "./components/CompWatch.vue";
import CompPropsComputeds from "./components/CompPropsComputeds.vue";
import CompEvents from "./components/CompEvents.vue";
import CompVmodel from "./components/CompVmodel.vue";
import CompVshow from "./components/CompVshow.vue";
import CompCondicionais from "./components/CompCondicionais.vue";

export default {
  name: "App",
  components: {
    TheHeader,
    CompVbind,
    CompWatch,
    CompPropsComputeds,
    CompEvents,
    CompVmodel,
    CompVshow,
    CompCondicionais,
  },
  data() {
    return {
      showHeader: true,
      user: {
        firstName: "Peter",
        lastName: "Lange",
      },
      showName: true,
      // accessLevel: "marketing",
      isHome: false,
      nameModel: "Seu Nome",
      selecao: "",
      colors: [],
    };
  },

  methods: {
    changeClass: () => (this.isHome = !this.isHome),
  },

  computed: {
    fullName() {
      return `${this.user.firstName} ${this.user.lastName}`;
    },
    cicomRG4() {
      return this.cicoms.filter((cicom) => cicom.RG);
    },
    cicomRG3() {
      return this.cicoms.filter((cicom) => !cicom.RG);
    },
  },

  watch: {
    // Propriedades que são observadas e chamam metodos
    nameWatch(newValue) {
      this.saveName(newValue);
    },
    pageCount() {
      this.changePage(this.pageCount);
    },
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}

.smallImg {
  width: 10rem;
}

.title {
  color: blue;
  font-size: 20px;
}
.title-home {
  color: green;
  font-size: 40px;
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

.coresSelecionadas {
  width: 50%;
}

.titulos {
  color: gray;
  font-size: 30px;
  font-weight: bold;
}
</style>
