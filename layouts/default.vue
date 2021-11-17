<template>
  <v-app>
    <v-navigation-drawer v-model="drawer" app light>
      <v-container>
        <h1 class="navigation-cart">Cart</h1>
        <br />
        <div class="cart-products">No hay Productos en el carrito :(</div>
      </v-container>
    </v-navigation-drawer>
    <v-app-bar app dense>
      <v-app-bar-nav-icon @click="drawer = !drawer"></v-app-bar-nav-icon>
      <v-spacer></v-spacer>
      <v-toolbar-title>Fake Shop</v-toolbar-title>

      <v-spacer></v-spacer>
      <div class="navigation-buttons">
        <!-- <v-cols cols="4">
          <v-bottom-navigation grow background-color="purple"
            >Home</v-bottom-navigation
          >
          <v-bottom-navigation grow background-color="purple"
            >Products</v-bottom-navigation
          >
          <v-bottom-navigation grow background-color="purple"
            >Cart</v-bottom-navigation
          >
        </v-cols> -->
      </div>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-app-bar>

    <v-main>
      <v-container>
        <Nuxt />
      </v-container>
    </v-main>
    <v-footer>
      <v-card>
        <v-divider></v-divider>

        <v-card-text class="white--text">
          {{ new Date().getFullYear() }} — <strong>Fake shop</strong>
        </v-card-text>
      </v-card>
    </v-footer>
  </v-app>
</template>

<script>
export default {
  data: () => ({ drawer: null }),
  cartproducts: [],
}
</script>

<style>
.navigation-cart {
  color: black;
  text-align: center;
}
.cart-products {
  color: black;
  text-align: center;
}
</style>
