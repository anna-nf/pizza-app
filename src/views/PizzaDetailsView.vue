<template>
  <div>
    <v-container>
      <v-card>
        <v-card-title class="text-h4">{{ pizzaDetails.name }}</v-card-title>
        <v-card-text>
          <p class="text-body-1">{{ pizzaDetails.details }}</p>
        </v-card-text>
        <v-card-actions>
          <v-btn color="primary" to="/">Zurück</v-btn>
          <v-spacer></v-spacer>
          <v-btn color="pink-lighten-1" @click="addToCart">
            <v-icon left>mdi-cart</v-icon>
            In den Warenkorb
          </v-btn>
        </v-card-actions>
      </v-card>

      <!-- Zweite Zeile mit Größenauswahl -->
      <v-row class="mt-6">
        <v-col cols="12">
          <h1 class="text-h5">Größe auswählen</h1>
          <v-radio-group v-model="selectedSize" inline>
            <p class="text-green-darken-2">
             Hier noch die v-radio mit label und value damit man die Größe der Pizza auswählen kann
            </p>
        </v-radio-group>

          <div class="mt-3 text-body-1">
            <strong>Ausgewählte Größe:</strong> {{ selectedSize }}
          </div>
        </v-col>
      </v-row>

    </v-container>
  </div>
</template>

<script setup>
import { computed, ref} from 'vue';
import { useRoute, useRouter } from 'vue-router';

const route = useRoute();
const router = useRouter();
const pizzaId = computed(() => route.params.id);
const selectedSize = ref('medium');

// Einfache Daten für die Pizzadetails
const pizzaData = {
  pepperoni: {
    name: 'Pepperoni Pizza',
    details: 'Die Pepperoni Pizza ist ein amerikanischer Klassiker mit würzigen Pepperoni-Scheiben. Sie wird mit unserer hausgemachten Tomatensauce, Mozzarella-Käse und scharfen Pepperoni-Scheiben zubereitet. Der Teig wird dünn ausgerollt und knusprig gebacken für ein authentisches Geschmackserlebnis.'
  },
  margherita: {
    name: 'Margherita Pizza',
    details: 'Die Margherita Pizza ist ein italienischer Klassiker, benannt nach Königin Margherita von Italien. Diese einfache aber köstliche Pizza wird mit frischen Tomaten, Mozzarella-Käse, Basilikum, Salz und Olivenöl zubereitet. Die Farbkombination repräsentiert die italienische Flagge: rot (Tomaten), weiß (Mozzarella) und grün (Basilikum).'
  }
};

// Computed property um die Details für die aktuelle Pizza zu erhalten
const pizzaDetails = computed(() => {
  return pizzaData[pizzaId.value] || { 
    name: 'Pizza nicht gefunden', 
    details: 'Die angeforderte Pizza existiert nicht in unserem Sortiment.'
  };
});

// SessionStorage statt localStorage verwenden
const addToCart = () => {
  // Erstellen eines Objekts für den Warenkorbeintrag
  const cartItem = {
    id: pizzaId.value,
    name: pizzaDetails.value.name,
    size: selectedSize.value,
  };
  
  // Aktuellen Warenkorb aus dem sessionStorage abrufen
  let cart = [];
  const savedCart = sessionStorage.getItem('pizzaCart');
  if (savedCart) {
    cart = JSON.parse(savedCart);
  }
  
  // Hinzufügen des neuen Eintrags zum Warenkorb
  cart.push(cartItem);
  
  // Speichern des aktualisierten Warenkorbs im sessionStorage
  sessionStorage.setItem('pizzaCart', JSON.stringify(cart));
  
  // Zum Warenkorb navigieren
  router.push('/cart');
};

// Auch die Warenkorb-Seite muss angepasst werden, um sessionStorage zu verwenden
</script>