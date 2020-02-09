<template>
  <div class="container">
    <app-quote-grid v-bind:quotes="quotes"></app-quote-grid>
  </div>
</template>

<script>
import Grid from "./components/Grid.vue";

export default {
  data: function() {
    return {
      quotes: [
        "La poesía es un arma cargada de futuro. La micropoesía es un arma cargada de pasado imperfecto. (Muy imperfecto)."
      ],
      maxQuotes: 10
    };
  },
  components: {
    appQuoteGrid: Grid
  }
};
</script>

<style>
@import "./css/style.css";
</style>
