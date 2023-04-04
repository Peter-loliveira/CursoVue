<template>
  <BaseAlert variant = 'danger' text = 'Texto inserido por PROPS' />

  <div class="card">
    Teste de Escopo
  </div>

  <CompBaseCard />
  <CompLifeStages /> 
  <TheHeader>
      
      <template v-slot:description>
        <h3>Descição: Via Slot description</h3>
      </template>
      <template v-slot:valor>
        <h3>Valor: Via Slot valor</h3>
      </template>
      
      <p>Total: Via Slot default</p>
      
  </TheHeader>

  <CompVshow />
  <CompVbind />
  <CompVmodel />
  <CompWatch />
  <CompEvents />
  <CompPropsComputeds />
  <CompCondicionais />
  <CompChangeClass />
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
import CompChangeClass from "./components/CompChangeClass.vue";
import CompLifeStages from "./components/CompLifeStages.vue";
import CompBaseCard from "@/components/CompBaseCard.vue";
import BaseAlert from "./components/BaseAlert.vue";

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
    CompChangeClass,
    CompLifeStages,
    CompBaseCard,
    BaseAlert
},
  data() {
    return {
      showHeader: true,
      showName: true,
    };
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

.titulos {
  color: gray;
  font-size: 30px;
  font-weight: bold;
}
</style>
