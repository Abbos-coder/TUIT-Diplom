<template>
  <section class="container">
    <h1 class="category__title text-center text-capitalize text-h4">
      категория Металлопрокат
    </h1>
    <v-row class="category__cards mt-5">
      <v-col
        cols="12"
        lg="3"
        md="4"
        sm="6"
        class="category__card"
        v-for="category in metals_type"
        :key="category.id"
      >
        <v-hover v-slot="{ hover }">
          <v-sheet
            elevation="3"
            class="category__card--block px-2 position-relative d-flex justify-center"
            min-height="295"
          >
            <img :src="category.image" :alt="category.name" />
            <v-overlay v-if="hover" absolute color="#c4e3ff">
              <v-btn
                to="/product/1"
                color="primary"
                rounded
                class="text-lowercase"
              >
                посмотреть все
              </v-btn>
            </v-overlay>
            <p class="text-center blue--text text--darken-3 px-2">
              {{ category.name }}
            </p>
          </v-sheet>
        </v-hover>
      </v-col>
    </v-row>
  </section>
</template>

<script>
export default {
  data: () => ({
    metals_type: [
      {
        id: 1,
        name: "Арматура",
        image:
          "https://files.glotr.uz/category/000/000/000/2020-05-19-12-48-26-915590-edb6526ce71af48d5f360ba9f0c6f4de.jpg?_=ozauc",
      },
      {
        id: 2,
        name: "Стальные балки",
        image:
          "https://files.glotr.uz/category/000/000/000/2020-05-19-13-21-34-216000-2e6197e8dae93b8bf755200b49ad90c0.jpg?_=ozauc",
      },
      {
        id: 3,
        name: "Проволоки",
        image:
          "https://files.glotr.uz/category/000/000/000/2020-05-19-13-01-24-000491-f7f6151769bdb13de59708fa91788c31.jpg?_=ozauc",
      },
      {
        id: 4,
        name: "Рулонные стали",
        image:
          "https://files.glotr.uz/category/000/000/000/2020-05-19-13-28-58-385050-c1775752780f692fe8b8d9c9fba62ede.jpg?_=ozauc",
      },
    ],
    overlay: false,
  }),
};
</script>

<style lang="scss" scoped>
@import "assets/scss/index";
html {
  font-family: "Poppins", sans-serif;
}
</style>
