<template>
  <nav class="navbar">
    <v-toolbar dense elevation="1" height="35">
      <v-row
        class="navbar container mx-auto px-n2"
        align="center"
        justify="center"
      >
        <div class="navbar__block mr-2">
          <div class="navbar__phone text-caption">
            <v-icon small color="blue darken-2" class="mr-1">mdi-phone</v-icon>
            <strong>
              <span>Call us now:</span>
              <a href="tel:+998994036828">+998 99 403-68-28</a>
            </strong>
          </div>
        </div>
        <v-spacer class="d-none d-sm-block"></v-spacer>
        <div class="navbar__block lang d-flex ml-1">
          <p class="text-body-2 mb-0"><span>UZ</span> | <span>RU</span></p>
          <div class="text-caption ml-4">
            <strong>Welcome, </strong>
            <nuxt-link to="/auth">Sign in</nuxt-link>
          </div>
        </div>
      </v-row>
    </v-toolbar>

    <div class="container mx-auto mt-md-n5 mt-sm-n2 navbar__controls">
      <div>
        <nuxt-link to="/">
          <img src="@/assets/img/logo.jpg" alt="logo" />
        </nuxt-link>
      </div>
      <div class="navbar__search mt-2">
        <v-text-field
          dense
          append-icon="mdi-magnify"
          label="Search"
          placeholder="Search..."
          solo
          class="mt-4"
        ></v-text-field>
      </div>
      <v-btn color="primary" class="ml-auto text-capitalize">
        <v-icon>mdi-cart</v-icon>
        <span>Your cart: 0</span>
      </v-btn>
    </div>

    <!-- <div>
      <ul class="container">
        <v-toolbar dark app>
          <v-toolbar-items class="hidden-sm-and-down">
            <v-btn v-for="item in menu" :key="item.icon" :to="item.link" flat>{{
              item.title
            }}</v-btn>
          </v-toolbar-items>
          <v-menu class="hidden-md-and-up">
            <v-toolbar-side-icon></v-toolbar-side-icon>
            <v-list>
              <v-list-tile v-for="item in menu" :key="item.icon">
                <v-list-tile-content>
                  <v-list-tile-title>{{ item.title }}</v-list-tile-title>
                </v-list-tile-content>
              </v-list-tile>
            </v-list>
          </v-menu>
        </v-toolbar>
      </ul>
    </div> -->
  </nav>
</template>

<script>
export default {
  data: () => ({
    menu: [
      { icon: "home", title: "Link A" },
      { icon: "info", title: "Link B" },
      { icon: "warning", title: "Link C" },
    ],
  }),
  methods: {
    menuItems() {
      return this.menu;
    },
  },
  mounted() {},
};
</script>

<style lang="scss" scoped>
body {
  font-family: Arial, Helvetica, sans-serif;
}
.v-toolbar {
  @media (max-width: 414px) {
    height: 60px !important;
    padding-top: 10px;
  }
  .lang {
    margin-top: 7px;
    a {
      text-decoration: none;
      font-weight: bold;
      margin-left: 5px;
    }
  }
  .navbar__phone {
    a {
      text-decoration: none;
      margin-left: 5px;
    }
  }
  .navbar__search {
    width: 100%;
  }
}
.navbar__controls {
  display: flex;
  align-items: center;
  justify-content: space-between;
}
</style>
