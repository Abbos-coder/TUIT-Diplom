<template>
  <v-app>
    <div class="auth container">
      <v-card width="400" class="mx-auto mt-10">
        <v-card-title>
          <h1 class="display-1">Login</h1>
        </v-card-title>
        <v-card-text>
          <v-form ref="form" v-model="valid" lazy-validation>
            <v-text-field
              label="Email"
              prepend-icon="mdi-account-circle"
              v-model="user.email"
              :rules="emailRules"
            ></v-text-field>
            <v-text-field
              label="Password"
              :type="showPass ? 'text' : 'password'"
              prepend-icon="mdi-lock"
              :append-icon="showPass ? 'mdi-eye' : 'mdi-eye-off'"
              @click:append="showPass = !showPass"
              v-model="user.password"
              :rules="[(v) => !!v || 'This is required']"
            ></v-text-field>
          </v-form>
        </v-card-text>
        <v-divider></v-divider>
        <v-card-actions>
          <v-btn to="/register" color="success" class="text-capitalize"
            >Register</v-btn
          >
          <v-spacer></v-spacer>
          <v-btn color="info" class="text-capitalize" @click="validate"
            >Login</v-btn
          >
        </v-card-actions>
      </v-card>
    </div>
  </v-app>
</template>

<script>
export default {
  layout: "noNavbar",
  data: () => ({
    valid: true,
    showPass: false,
    emailRules: [
      (v) => !!v || "E-mail kiriting",
      (v) => /.+@.+\..+/.test(v) || "Tog'ri E-mail kiriting",
    ],
    user: {
      email: "",
      password: "",
    },
  }),
  methods: {
    async validate() {
      const auth = this.$refs.form.validate();
      if (auth) {
        try {
          const user = this.user;
          await this.$axios.$post("/api/auth", user, {
            headers: {
              "Content-Type": "application/json",
            },
          });
        } catch (error) {
          console.log(error);
        }
      }
    },
  },
};
</script>

<style lang="scss" scoped></style>
