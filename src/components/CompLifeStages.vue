<template>
  <div>
    <h1>Componente que exibe LOGS nas fazes de criação do componente</h1>
  </div>
</template>

<script>
  export default{
    name: "CompLifeStages",
    data(){
      return {
        name: 'Peter Lange',
      }
    },
    beforeCreate(){
      console.log(this.name);
      console.log(this.$el);
    },
    created(){
      console.log(this.name);
      console.log(this.$el);
    },
    beforeMount(){
      console.log(this.name);
      console.log(this.$el);
    },
    mounted(){
      console.log(this.name);
      console.log(this.$el);
    },
    beforeUnmount(){
      console.log(this.name);
      console.log(this.$el);
    },
    unmounted(){
      console.log(this.name);
      console.log(this.$el);
    },
  }
</script>

<style>

</style>
