<template>
   <section class="category container">
      <h1 class="category__title text-center text-capitalize text-h4">
         категория стройматериалов
      </h1>
      <v-row class="category__cards mt-5">
         <v-col
            cols="12"
            lg="3"
            md="4"
            sm="6"
            class="category__card"
            v-for="category in categories"
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
                        :to="category.link"
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
      categories: [
         {
            id: 1,
            name: "Металлопрокат",
            link: "product",
            image: "https://files.glotr.uz/category/000/000/000/2020-01-06-15-44-01-076815-4a122cfe3ef5a048500fcd9a1f65e31f.jpg?_=ozauc",
         },
         {
            id: 2,
            name: "Лакокрасочная продукция",
            link: "paint-products",
            image: "https://files.glotr.uz/category/000/000/000/2020-01-06-15-48-00-066710-4e63d6cc61f0415495ef9458f63642cf.jpg?_=ozauc",
         },
         {
            id: 3,
            name: "Сухие строительные смеси",
            link: "dry-mixes",
            image: "https://files.glotr.uz/category/000/000/000/2020-01-06-15-33-24-631905-7fd4389d83a0fad7454fa619dee32ede.jpg?_=ozauc",
         },
         {
            id: 4,
            name: "Утеплители",
            link: "heaters",
            image: "https://files.glotr.uz/category/000/000/000/2020-01-06-15-32-52-120294-792d1d7a1061c5059d730ed564a48ae1.jpg?_=ozauc",
         },
         {
            id: 5,
            name: "Герметики",
            link: "sealants",
            image: "https://files.glotr.uz/category/000/000/000/2020-01-06-15-39-26-030508-d7f3c8be624918d0d2a4140a7d4f0c05.jpg?_=ozauc",
         },
         {
            id: 6,
            name: "Стекла",
            link: "glass",
            image: "https://files.glotr.uz/category/000/000/000/2020-01-06-15-47-53-793650-5a3c32e3fc552bd719a0e70997af3658.jpg?_=ozauc",
         },
         {
            id: 7,
            name: "Сыпучие строительные материалы",
            link: "bulk-building-materials",
            image: "https://files.glotr.uz/category/000/000/000/2020-01-06-15-47-44-161495-dcd5c53c6ab21d323fbd0f722570aa23.jpg?_=ozauc",
         },
         {
            id: 8,
            name: "Монтажные пены",
            link: "mounting-foams",
            image: "https://files.glotr.uz/category/000/000/000/2020-01-06-15-33-19-845699-96a4582cc9a624dafb6ccb2f80c93d44.jpg?_=ozauc",
         },
         {
            id: 9,
            name: "Освещение и световые приборы",
            link: "lighting-fixtures",
            image: "https://files.glotr.uz/category/000/000/000/2020-01-06-15-28-37-439260-60e76834a953ad643cfe16e72da946ff.jpg?_=ozauc",
         },
         {
            id: 10,
            name: "Кладочные материалы",
            link: "masonry-materials",
            image: "https://files.glotr.uz/category/000/000/000/2020-01-06-15-47-26-321740-8497f3bbf79e047ffae7550543d5aae0.jpg?_=ozauc",
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
