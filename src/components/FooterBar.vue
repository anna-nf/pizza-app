<template>
    <v-bottom-navigation
      grow
      height="64"
      app
    >
      <v-btn
        :to="'/'"
        value="home"
      >
        <v-icon>mdi-home</v-icon>
        <span>Home</span>
      </v-btn>
  
      <p class="text-green-darken-2">füge hiere ein v-btn mit dass den user zu den Warenkorb weiterleitet</p>
    </v-bottom-navigation>

  </template>
  
  <script setup>
  </script>
  
  <style scoped>
  .v-bottom-navigation span {
    font-size: 0.75rem;
  }
  </style>
  