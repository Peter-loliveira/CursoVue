<template>
  <div>
    <h1 class="titulos">v-if / v-else-if / v-else</h1>
    <select v-model="accessLevel">
        <option value="administrador">Administradores</option>
        <option value="marketing">Equipe de Marketing</option>
        <option value="ti">Equipe Técnica</option>
        <option value="financeiro">Equipe Financeira</option>
    </select>
    <br>
    <label v-if = "accessLevel === 'administrador'" >Administrador</label>
    <label v-else-if = "accessLevel === 'marketing'" >Equipe de Marketing</label>
    <label v-else-if = "accessLevel === 'ti'" >Equipe Técnica</label>
    <label v-else>Equipe Financeira</label>
  </div>
  <hr>
</template>

<script>
    export default {
        name: "CompCondicionais",
        data(){
            return {
                accessLevel: ''
            }
        }
    }
</script>

<style>
select, label {
    margin-bottom: 5px;
}

</style>