<template>
  <div class="cabecalho">
    <h1 v-if = "$slots.title">
      <slot name = 'title'/>
    </h1>
    <slot name = 'description'/>
    <slot name = 'valor'/>
    <slot />
  </div>
</template>

<script>
export default {
  name: "TheHeader",
  mounted(){
    console.log(this.$slots);
  }
};

</script>

<style>


.cabecalho {
  background-color: #000;
  color: #fff;
  font-size: 20px;
  padding: 10px;
}
b{
  color: gray;
}
</style>
