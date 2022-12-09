<template white>
  <v-card id="lateral">
    <v-toolbar

      tabs
      flat
      color="indigo"
    >
    <div class="text-center">
      <v-toolbar-title>Carnet de bord</v-toolbar-title>
    </div>
      <v-spacer></v-spacer>

      <template v-slot:extension>
        <v-tabs
          v-model="tabs"
          align-with-title
        >
          <v-tab href="#one">
            Clinique
          </v-tab>
          <v-tab href="#two">
            Propiétaire
          </v-tab>
          <v-tab href="#three">
            Animal
          </v-tab>
          <v-tabs-slider color="pink"></v-tabs-slider>
        </v-tabs>
      </template>
    </v-toolbar>
    <v-card-text>
      <v-tabs-items v-model="tabs">
        <v-tab-item
          v-for="content in ['one', 'two', 'three']"
          :key="content"
          :value="content"
        >
          <v-card
            height="200px"
            flat
          >
          </v-card>
        </v-tab-item>
      </v-tabs-items>
    </v-card-text>

  </v-card>
</template>
<script>
  export default {
    data: () => ({
      fab: false,
      hidden: false,
      tabs: null,
    }),

    computed: {
      activeFab () {
        switch (this.tabs) {
          case 'one': return { color: 'success', icon: 'mdi-share-variant' }
          case 'two': return { color: 'red', icon: 'mdi-pencil' }
          case 'three': return { color: 'green', icon: 'mdi-chevron-up' }
          default: return {}
        }
      },
    },
  }
</script>
<style>
  /* This is for documentation purposes and will not be needed in your application */
  #lateral .v-btn--example {
    bottom: 0;
    position: absolute;
    margin: 0 0 16px 16px;
  }
</style>

