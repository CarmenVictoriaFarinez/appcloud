<template>
  <v-card
    flat
    height="70px"
    tile
  >
    <v-toolbar dense>
      <v-toolbar-title>
            <img 
            :src="require('../assets/logo.png')" 
            alt='Logo'
            class="logo">
      </v-toolbar-title>

      <v-spacer></v-spacer>

      <v-btn icon>
        <v-icon>mdi-magnify</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-heart</v-icon>
      </v-btn>

      <v-btn icon>
        <v-icon>mdi-dots-vertical</v-icon>
      </v-btn>
    </v-toolbar>
  </v-card>
</template>
