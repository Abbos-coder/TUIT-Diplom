<template>
  <div class="container">
    <h1 class="text-center text-h4 mt-3 text-capitalize">корзина</h1>
    <v-card elevation="2">
      <v-row class="mt-4">
        <v-col cols="12" lg="4" xs="12" class="d-flex justify-center">
          <img
            src="https://files.glotr.uz/company/000/005/189/products/2019/10/21/15716530615269-4a0296e0f440d2141ce181f59112dbbd.jpg?_=ozauc"
            alt="product-img"
          />
        </v-col>
        <v-col>
          <v-card-title>Арматура 35 гс А-400 д. 18</v-card-title>
          <v-card-subtitle>8,540,000 <span>sum</span></v-card-subtitle>
          <v-card-text>
            Lorem ipsum dolor sit amet consectetur, adipisicing elit. Impedit
            molestias, numquam modi quidem autem quis? Fuga, nemo! Magni quo
            ipsum architecto ipsam vel provident, eaque illum similique aliquid
            deserunt id!
          </v-card-text>
          <v-card-actions>
            <v-btn color="error" small>
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
    product: {
      id: 1,
      image:
        "https://files.glotr.uz/company/000/005/189/products/2019/10/21/15716530615269-4a0296e0f440d2141ce181f59112dbbd.jpg?_=ozauc",
      rating: 3.5,
      name: "Арматура 35 гс А-400 д. 18",
      price: 8717452,
      status: true,
    },
  }),
  computed: {
    basket() {
      return this.$store.state.basket;
    },
  },
};
</script>

<style lang="scss" scoped></style>
