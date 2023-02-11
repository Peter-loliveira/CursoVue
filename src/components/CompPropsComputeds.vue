<template>
  <div>
      <h1 class="titulos">Propriedades Computadas</h1>
      {{ fullName }}
    <h2>Cicoms RG4</h2>
    <ul>
        <li v-for = "cicom in cicomRG4" :key = "cicom.circuito">
            <input type="checkbox" v-model = "cicom.RG">
            {{ cicom.cicom }} / <b>{{ cicom.circuito }}</b>
        </li>
    </ul>
    <h2>Cicoms RG3</h2>
    <ul>
        <li v-for = "cicom in cicomRG3" :key = "cicom.circuito">
            <input type="checkbox" v-model = "cicom.RG">
            {{ cicom.cicom }} / <b>{{ cicom.circuito }}</b>
        </li>
    </ul>
    <hr>
  </div>
</template>

<script>
export default {
  name: "CompPropsComputeds",
  data() {
    return {
      user: {
        firstName: "Peter",
        LastName: "Lange",
      },
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
    };
  },
  computed: {
    fullName() {
      return `${this.user.firstName} ${this.user.LastName}`
    },
    cicomRG4() {
        return this.cicoms.filter((cicom) => cicom.RG)
    },
    cicomRG3() {
        return this.cicoms.filter((cicom) => !cicom.RG)
    },
  },
};
</script>

<style>
li{
    list-style-type: none;
    text-align: left;
    margin-left: 40%;
}

.smallImg {
  width: 10rem;
}
</style>
