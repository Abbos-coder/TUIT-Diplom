<template>
  <div class="container">
    <h1 class="text-center text-h4 mt-3 text-capitalize">корзина</h1>
    <h3 class="text-center text-h6 warning--text mt-10" v-if="!products.length">
      Продукт ешо не выбран!
    </h3>
    <v-card elevation="2" v-else>
      <v-row class="mt-4" v-for="(item, idx) in products" :key="idx">
        <v-col cols="12" lg="4" xs="12" class="d-flex justify-center">
          <img :src="item.image" :alt="item.name" />
        </v-col>
        <v-col>
          <v-card-title>{{ item.name }}</v-card-title>
          <v-card-subtitle
            >{{ item.price.toLocaleString("en-US") }}
            <span>sum</span></v-card-subtitle
          >
          <v-card-text>
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Impedit
            molestias, numquam modi quidem autem quis? Fuga, nemo! Magni quo
            ipsum architecto ipsam vel provident, eaque illum similique aliquid
            deserunt id!
          </v-card-text>
          <v-card-actions>
            <v-btn color="error" small @click="removeProduct(idx)">
              удалить
              <v-icon size="18">mdi-delete-empty</v-icon>
            </v-btn>
            <v-btn color="success" small>
              купить
              <v-icon size="18">mdi-currency-usd</v-icon>
            </v-btn>
          </v-card-actions>
        </v-col>
      </v-row>
    </v-card>
  </div>
</template>

<script>
export default {
  layout: "noFooter",
  data: () => ({
    products: [],
  }),
  computed: {
    basket() {
      return this.$store.state.basket;
    },
  },
  methods: {
    removeProduct(selected) {
      this.$store.commit("deleteProduct", selected);
    },
  },
  mounted() {
    this.products = this.$store.state.basket;
  },
};
</script>

<style lang="scss" scoped></style>
