<template>
  <div class="container product">
    <h1 class="text-center mb-5">Арматури</h1>
    <v-row>
      <v-col
        cols="12"
        lg="3"
        md="4"
        sm="6"
        v-for="product in products"
        :key="product.id"
      >
        <div class="product__card">
          <div class="product__card--image">
            <img :src="product.image" :alt="product.name" />
          </div>
          <div class="product__name">{{ product.name }}</div>
          <div class="product__price">
            {{ product.price.toLocaleString("en-US") }} <span>сум /</span
            ><span> тонна</span>
          </div>
          <v-rating
            v-model="product.rating"
            color="yellow darken-3"
            background-color="grey darken-1"
            empty-icon="$ratingFull"
            half-increments
            size="20"
            hover
          ></v-rating>
          <v-btn
            color="primary"
            class="mt-1 mb-3"
            small
            @click.prevent="$router.push(`/product-info/1`)"
            >подробно</v-btn
          >
          <div
            class="product__status ml-3 green--text text--accent-4 text-caption align-self-start"
          >
            {{ product.status ? "в наличии" : "нет в наличии" }}
          </div>
        </div>
      </v-col>
    </v-row>
  </div>
</template>

<script>
export default {
  data() {
    return {
      products: [
        {
          id: 1,
          image:
            "https://files.glotr.uz/company/000/005/189/products/2019/10/21/15716530615269-4a0296e0f440d2141ce181f59112dbbd.jpg?_=ozauc",
          rating: 3.5,
          name: "Арматура 35 гс А-400 д. 18",
          price: 8717452,
          status: true,
        },
        {
          id: 2,
          image:
            "https://files.glotr.uz/company/000/012/760/products/2020/07/14/2020-07-14-18-16-42-967773-9a732e2d3f6b1eb9af4cd171f80721e8.jpeg?_=ozauc",
          rating: 3.5,
          name: "Арматуры №12 мм",
          price: 8717452,
          status: true,
        },
        {
          id: 3,
          image:
            "https://files.glotr.uz/company/000/011/446/products/2021/10/22/2021-10-22-15-12-57-069570-bb322f8ebec2bf754f5063087d90a85f.jpg?_=ozauc",
          rating: 3.5,
          name: "Арматура",
          price: 8717452,
          status: true,
        },
        {
          id: 4,
          image:
            "https://files.glotr.uz/company/000/008/190/products/2018/10/09/15390901020938-e41f012d6658abce8b718752db4eec3d.jpg?_=ozauc",
          rating: 3.5,
          name: "Арматура 10 (Бекабад)",
          price: 8717452,
          status: false,
        },
        {
          id: 5,
          image:
            "https://files.glotr.uz/company/000/024/265/products/2021/11/06/2021-11-06-13-12-51-653923-564f1b1a945508536da46ee049473c4b.jpg?_=ozauc",
          rating: 3.5,
          name: "Арматура рифленая А500 от 8 мм до 42 мм (Россия)",
          price: 8717452,
          status: true,
        },
        {
          id: 6,
          image:
            "https://files.glotr.uz/company/000/013/126/products/2019/11/19/15741544653798-1014a7a84ca085183f6fab7ec62be142.jpg?_=ozauc",
          rating: 3.5,
          name: "Арматура (в оптом по перечислению)",
          price: 8717452,
          status: false,
        },
      ],
    };
  },
};
</script>

<style lang="scss" scoped>
@import "assets/scss/product";
</style>
