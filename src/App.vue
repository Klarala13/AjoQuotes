<template>
  <div class="container">
    <new-quote @addingQuote="newQuote"></new-quote>
    <app-quote-grid
      v-bind:quotes="quotes"
      v-on:quoteDeleted="deleteQuote"
    ></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
      </div>
    </div>
  </div>
</template>

<script>
//
import Grid from "./components/Grid.vue";
import NewQuote from "./components/NewQuote.vue";

export default {
  data: function() {
    return {
      quotes: [
        "La poesía es un arma cargada de futuro. La micropoesía es un arma cargada de pasado imperfecto. (Muy imperfecto).",
        "Siempre siempre siempre siempre siempre siempre siempre siempre siempre siempre y aún así me parece poco."
      ],
      maxQuotes: 20
    };
  },
  methods: {
    newQuote(quote) {
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
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
