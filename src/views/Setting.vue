<template>
<div align="center">
  <v-card flat max-width="300">
    <v-toolbar flat height="72">
      <v-switch
        v-model="$vuetify.theme.dark"
        inset
        label="Vuetify Theme"
        persistent-hint
      ></v-switch>
    </v-toolbar>
  </v-card>
  </div>
</template>