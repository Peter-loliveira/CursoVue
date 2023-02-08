<template>
  <h1 class="titulos">V-Show</h1>
  <TheHeader v-if="showHeader" />
  <hr />

  <div>
    <h1 class="titulos">Watch</h1>
    <input type="text"
      v-model = "nameWatch"
    >
    <h2>{{ nameWatch }}</h2>

    <select v-model = "pageCount">
      <option value="5">5</option>
      <option value="10">10</option>
      <option value="15">15</option>
    </select>
    <br>
    <label>{{ pageCount }}</label>
  </div>
  <hr>

  <div>
    <h1 class="titulos">Propriedades Computadas</h1>
    {{ fullName }}
    <br />

    <h2>Cicoms RG4</h2>
    <ul>
      <li>CICOM / CIRCUITO</li>
      <li v-for="cicom in cicomRG4" :key="cicom.circuito">
        <input type="checkbox" v-model="cicom.RG" />
        {{ cicom.cicom }} / <b>{{ cicom.circuito }}</b>
      </li>
    </ul>
    <h2>Cicoms RG3</h2>
    <ul>
      <li>CICOM / CIRCUITO</li>
      <li v-for="cicom in cicomRG3" :key="cicom.circuito">
        <input type="checkbox" v-model="cicom.RG" />
        {{ cicom.cicom }} / <b> {{ cicom.circuito }}</b>
      </li>
    </ul>
  </div>
  <hr />

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

  <div>
    <h1 class="titulos">V-Model</h1>
    <label for="">Nome: </label>
    <input v-model="nameModel" type="text" />
    <br />
    <label for="">{{ nameModel }}</label>
    <br />
    <select v-model="selecao" name="" id="">
      <option value="">Selecione uma opção</option>
      <option value="Opção 1">Opção 1</option>
      <option value="Opção 2">Opção 2</option>
      <option value="Opção 3">Opção 3</option>
      <option value="Opção 4">Opção 4</option>
      <option value="Opção 5">Opção 5</option>
    </select>
    <input type="text" v-model="selecao" />
    <br />

    <div>
      <label for="">Opções</label>
      <input v-model="colors" type="checkbox" name="" id="" value="Amarelo" />
      Amarelo
      <input v-model="colors" type="checkbox" name="" id="" value="Azul" />
      Azul
      <input v-model="colors" type="checkbox" name="" id="" value="Vermelho" />
      Vermelho
      <input v-model="colors" type="checkbox" name="" id="" value="Preto" />
      Branco
      <input v-model="colors" type="checkbox" name="" id="" value="Branco" />
      Branco
      <p>Cores Selecionadas</p>
      <input class="coresSelecionadas" type="text" :value="colors" />
    </div>
  </div>
  <hr />

  <div>
    <h1 class="titulos">v-show</h1>
    <div v-show="showName">
      Nome: {{ this.user.firstName }} <br />
      Sobrenome: {{ this.user.lastName }}
    </div>
  </div>
  <hr />

  <div>
    <h1 class="titulos">v-if / v-else-if / v-else</h1>
    <div v-if="accessLevel === 'admin'">Admionistrador</div>
    <div v-else-if="accessLevel === 'marketing'">Equipe de Marketing</div>
    <div v-else>User</div>
  </div>
  <hr />

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
    <h1 class="titulos">V-Bind</h1>
    <div>
      <input v-model="imgSrc" type="text" />
      <br />

      <img :src="imgSrc" :alt="imgAlt" class="smallImg" />
    </div>
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

  <!-- <img alt="Vue logo" src="./assets/logo.png" /> -->
  <!-- <HelloWorld msg="Bem vindo ao seu APP em Vue.js App" /> -->
</template>

<script>
// import HelloWorld from "./components/HelloWorld.vue";
import TheHeader from "./components/TheHeader.vue";

export default {
  name: "App",
  components: {
    // HelloWorld,
    // eslint-disable-next-line vue/no-unused-components
    TheHeader,
  },
  data() {
    return {
      pageCount: 5,
      showHeader: true,
      user: {
        firstName: "Peter",
        lastName: "Lange",
      },
      showName: true,
      accessLevel: "marketing",
      imgSrc:
      "https://upload.wikimedia.org/wikipedia/commons/7/7e/Doctor_Who_Logo_1973-1980.svg",
      imgAlt: "Foto do Jon Snow",
      isHome: false,
      nameModel: "Seu Nome",
      selecao: "",
      colors: [],
      cicoms: [
        {
          cicom: "Alagoinhas",
          circuito: "ALGRG0028I",
          RG: true,
          Tel: "(75)3423-9200",
        },
        {
          cicom: "Barreiras",
          circuito: "BES5031525",
          RG: true,
          Tel: "(77)3611-0190",
        },
        {
          cicom: "Barreiras",
          circuito: "BRSRG0027I",
          RG: true,
          Tel: "(77)3611-0190",
        },
        {
          cicom: "Brumado",
          circuito: "BMDRG0010I",
          RG: true,
          Tel: "(77)3453-2649",
        },
        {
          cicom: "Esplanada",
          circuito: "ESPRG0006I",
          RG: true,
          Tel: "(77)3413-7600",
        },
        {
          cicom: "Euclides da Cunha",
          circuito: "ECNRG0010I",
          RG: true,
          Tel: "(75)32710190",
        },
        {
          cicom: "Feira de Santana",
          circuito: "FRSRG0074I",
          RG: true,
          Tel: "(75)3224-0918",
        },
        {
          cicom: "Guanambi",
          circuito: "GNB5017824",
          RG: true,
          Tel: "(77)3451-5399",
        },
        {
          cicom: "Guanambi",
          circuito: "GMBRG0014I",
          RG: true,
          Tel: "(77)3451-5399",
        },
        {
          cicom: "Ibotirama",
          circuito: "ITMRG0006I",
          RG: true,
          Tel: "(77)3698-6500",
        },
        {
          cicom: "Irecê",
          circuito: "IRCRG0019I",
          RG: true,
          Tel: "(74)3641-5935",
        },
        {
          cicom: "Itaberaba",
          circuito: "ITRRG0018I",
          RG: true,
          Tel: "(75)3251-8450",
        },
        {
          cicom: "Itabuna",
          circuito: "ITBRG0036I",
          RG: true,
          Tel: "(73)32141500",
        },
        {
          cicom: "Jequié",
          circuito: "JQERG0035I",
          RG: true,
          Tel: "(73)3528-3900",
        },
        {
          cicom: "Juazeiro",
          circuito: "JUARG0041I",
          RG: true,
          Tel: "(74)3611-9230",
        },
        {
          cicom: "Paulo Afonso",
          circuito: "PAFRG0023I",
          RG: true,
          Tel: "(75)3281-8900",
        },
        {
          cicom: "Porto Seguro",
          circuito: "PGU5022195",
          RG: true,
          Tel: "(73)3268-9330",
        },
        {
          cicom: "Porto Seguro",
          circuito: "PSGRG0020I",
          RG: true,
          Tel: "(73)3268-9330",
        },
        {
          cicom: "Santa Maria da Vitoria",
          circuito: "SMVRG0014I",
          RG: true,
          Tel: "(77)3483-6549",
        },
        {
          cicom: "Santo Antônio de Jesus",
          circuito: "SAJRG0016I",
          RG: true,
          Tel: "(75)3631-8450",
        },
        {
          cicom: "Senhor do Bonfim",
          circuito: "SDBRG0018I",
          RG: true,
          Tel: "(74)3541-3995",
        },
        {
          cicom: "Serrinha",
          circuito: "SRRRG0019I",
          RG: true,
          Tel: "(75) 3261-8247",
        },
        {
          cicom: "Teixeira de Freitas",
          circuito: "TXFRG0020I",
          RG: true,
          Tel: "(73)3165-2199",
        },
        {
          cicom: "Valença",
          circuito: "VEC5015775",
          RG: true,
          Tel: "(75)36433400",
        },
        {
          cicom: "Valença",
          circuito: "VLCRG0018I",
          RG: true,
          Tel: "(75)36433400",
        },
        {
          cicom: "Vitoria da Conquista",
          circuito: "VCARG0038I",
          RG: true,
          Tel: "(77) 3420-8800",
        },
      ],
      nameWatch: '',
    };
  },

  methods: {
    changeClass: () => (this.isHome = !this.isHome),
    submeter: (event) => {
      alert("Formulário Enviado");
      console.log(event);
    },
    //metodo a ser chamado pela propriedade Watch
    saveName: (nome) => {
      if(nome.length >= 5){
        alert(nome)
      }
    },
    changePage(value){
      alert(`Quantidade de páginas ${value} selecionadas!`)
    }
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
      this.saveName(newValue)
    },
    pageCount(){
      this.changePage(this.pageCount)
    },
  }
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
