<template>
  <v-app dark>
    <v-main>
      <Navbar />
      <Nuxt />
      <Sidebar />
      <Footer />
    </v-main>
  </v-app>
</template>

<script>
export default {
  name: "DefaultLayout",
  data() {
    return {};
  },
  mounted() {
    const user = localStorage.getItem("user");
    user ? (this.$store.state.logged_in = true) : null;
  },
};
</script>

<style lang="scss" scoped>
.navbar {
  position: -webkit-sticky;
  position: sticky;
  z-index: 10;
}
html {
  font-family: "Poppins", sans-serif;
}

// .layout-enter-active,
.page-enter-active {
  animation: acrossIn 0.4s ease-out both;
}
.layout-leave-active,
.page-leave-active {
  animation: acrossOut 0.6s ease-in both;
}
@keyframes acrossIn {
  0% {
    transform: translate3d(100%, 0, 0);
  }
  100% {
    transform: translate3d(0, 0, 0);
  }
}
@keyframes acrossOut {
  0% {
    transform: translate3d(0, 0, 0);
  }
  100% {
    transform: translate3d(-100%, 0, 0);
  }
}
</style>
