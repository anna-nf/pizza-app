<template>
  <div>
    <v-container>
      <v-row>
        <v-col cols="12" md="6">
          <v-card>
            <v-card-text class="text-green-darken-2">
              Hier brauchen wir: v-img, v-card-title und v-card-text</v-card-text
              </v-card-text
            >
            <v-card-actions>
              <v-btn
                color="primary"
                :to="{ name: 'pizza-details', params: { id: 'pepperoni' } }"
                >Details</v-btn
              >
            </v-card-actions>
          </v-card>
        </v-col>
        <v-col cols="12" md="6">
          <v-card>
            <v-card-text class="text-green-darken-2"
              >Hier brauchen wir: v-img, v-card-title und
              v-card-text</v-card-text
            >
            <v-card-actions>
              <v-btn
                color="primary"
                :to="{ name: 'pizza-details', params: { id: 'margherita' } }"
                >Details</v-btn
              >
            </v-card-actions>
          </v-card>
        </v-col>
      </v-row>
    </v-container>
  </div>
</template>

<script setup></script>
