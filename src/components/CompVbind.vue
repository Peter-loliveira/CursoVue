<template>
  <div>
    <h1 class="titulos">V-Bind</h1>
    <div>
      <input v-model="imgSrc" type="text" />
      <br />

      <img :src="imgSrc" :alt="imgAlt" class="smallImg" />
    </div>
  </div>
  <hr />
</template>

<script>
export default {
    // eslint-disable-next-line vue/multi-word-component-names
    name: "CompVbind",
  data() {
    return {
      imgSrc: "https://upload.wikimedia.org/wikipedia/commons/7/7e/Doctor_Who_Logo_1973-1980.svg",
      imgAlt: "Foto dinâmica",
    };
  },
};
</script>

<style></style>
