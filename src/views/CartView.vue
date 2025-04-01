<template>
  <div>
    <v-container>
      <h3 class="text-h3 mb-6">Warenkorb</h3>
      
      <v-card v-if="cart.length > 0">
        <v-list>
          <v-list-item
            v-for="(item, index) in cart"
            :key="index"
          >
            <v-list-item-title>
              {{ item.name }} - Größe: {{ item.size }}
            </v-list-item-title>
            <v-list-item-action>
              <v-btn
                icon
                color="red"
                @click="removeFromCart(index)"
              >
                <v-icon>mdi-delete</v-icon>
              </v-btn>
            </v-list-item-action>
          </v-list-item>
        </v-list>
        
        <v-card-actions>
          <v-btn color="error" @click="clearCart">
            <v-icon left>mdi-delete-sweep</v-icon>
            Warenkorb leeren
          </v-btn>
          <v-spacer></v-spacer>
          <v-btn color="primary" to="/">
            Weiter einkaufen
          </v-btn>
        </v-card-actions>
      </v-card>
      
      <v-card v-else class="pa-4 text-center">
        <p>Ihr Warenkorb ist leer.</p>
        <v-btn color="primary" to="/" class="mt-2">
          Zur Speisekarte
        </v-btn>
      </v-card>
    </v-container>
  </div>
</template>

<script setup>
import { ref, onMounted } from 'vue';

// In einer echten Anwendung würde dies mit einem Store wie Pinia oder Vuex verwaltet
const cart = ref([]);

// Funktion zum Laden des Warenkorbs aus dem sessionStorage
const loadCart = () => {
  const savedCart = sessionStorage.getItem('pizzaCart');
  if (savedCart) {
    cart.value = JSON.parse(savedCart);
  }
};

// Funktion zum Entfernen eines einzelnen Eintrags aus dem Warenkorb
const removeFromCart = (index) => {
  cart.value.splice(index, 1);
  updateSessionStorage();
};

// Funktion zum Leeren des gesamten Warenkorbs
const clearCart = () => {
  cart.value = [];
  updateSessionStorage();
};

// Hilfsfunktion zum Aktualisieren des sessionStorage
const updateSessionStorage = () => {
  sessionStorage.setItem('pizzaCart', JSON.stringify(cart.value));
};

// Beim Laden der Seite den Warenkorb aus dem sessionStorage laden
onMounted(() => {
  loadCart();
});
</script>