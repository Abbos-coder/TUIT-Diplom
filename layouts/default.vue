<template>
  <v-app dark>
    <v-main>
      <Nuxt />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "DefaultLayout",
  data() {
    return {};
  },
};
</script>

<style lang="scss" scoped>
html {
  font-family: "Poppins", sans-serif;
}
</style>
