<template>
  <div class="about">
    <h1>About Our Pizza App</h1>
    <p>Welcome to the premier destination for pizza lovers!</p>
    
    <v-container>
      <v-row>
        <v-col cols="12" md="8">
          <h2>Our Story</h2>
          <p>
            Diese App wurde im Rahmen des Girls' Day 2025 zusammen mit talentierten jungen Teilnehmerinnen entwickelt.
            Das Projekt zeigt, wie moderne Webtechnologien genutzt werden können, um interaktive Anwendungen zu erstellen.
          </p>
          <p>
            Unser Team hat diese Pizza-App von Grund auf konzipiert und umgesetzt, um den Bestellprozess
            für Pizza-Liebhaber so einfach und angenehm wie möglich zu gestalten.
          </p>
          <p>
            Wir hoffen, dass dieses Projekt die Begeisterung für Technologie und Softwareentwicklung
            weckt und junge Menschen dazu inspiriert, die digitale Zukunft mitzugestalten.
          </p>
        </v-col>
        <v-col cols="12" md="4">
          <v-card>
            <v-card-title>Contact Us</v-card-title>
            <v-card-text>
              <p>Email: info@pizzaapp.com</p>
              <p>Phone: (123) 456-7890</p>
              <p class="font-weight-bold">Netfonds AG</p>
              <p>Heidenkampsweg 73</p>
              <p>20097 Hamburg</p>
            </v-card-text>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script>
export default {
  name: 'AboutView'
}
</script>

<style scoped>
.about {
  padding: 20px;
}

h1 {
  margin-bottom: 20px;
  color: #e53935;
}

h2 {
  margin-bottom: 15px;
  color: #d81b60;
}

p {
  margin-bottom: 12px;
  line-height: 1.6;
}
</style>