<script setup>
import NavigationBar from './components/NavigationBar.vue';
import FooterBar from './components/FooterBar.vue';
import '@mdi/font/css/materialdesignicons.css'
</script>

<template>
  <v-app>
    <NavigationBar />

    <v-main>
      <v-container>
        <router-view />
      </v-container>
    </v-main>

    <FooterBar />
  </v-app>
</template>


