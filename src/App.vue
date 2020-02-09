<template>
  <div class="container">
    <new-quote @addingQuote="newQuote"></new-quote>
    <app-quote-grid v-bind:quotes="quotes"></app-quote-grid>
  </div>
</template>

<script>
//Siempre siempre siempre siempre siempre siempre siempre siempre siempre siempre y aún así me parece poco.
//La poesía es un arma cargada de futuro. La micropoesía es un arma cargada de pasado imperfecto. (Muy imperfecto).

import Grid from "./components/Grid.vue";
import NewQuote from "./components/NewQuote.vue";

export default {
  data: function() {
    return {
      quotes: [
        "La poesía es un arma cargada de futuro. La micropoesía es un arma cargada de pasado imperfecto. (Muy imperfecto)."
      ],
      maxQuotes: 10
    };
  },
  methods: {
    newQuote(quote) {
      this.quotes.push(quote);
    }
  },
  components: {
    appQuoteGrid: Grid,
    newQuote: NewQuote
  }
};
</script>

<style>
@import "./css/style.css";
</style>
