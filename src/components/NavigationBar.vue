<template>
  <v-app-bar>
    <v-container class="d-flex align-center">
        <router-link to="/" class="text-decoration-none">
        <img
          src="../assets/images/girls-app-new.png"
          alt="Pizza Logo"
          height="100"
      </router-link>
      <v-spacer></v-spacer>
      <v-btn to="/" text>Home</v-btn>
      <v-btn to="/about" text>About</v-btn>
      <p class="text-green-darken-2">Hier muss 
        router-link, v-icon mit einem mdi-cart, ähnlich wie
        beim logo -->
       </p>
    </v-container>
  </v-app-bar>
</template>

