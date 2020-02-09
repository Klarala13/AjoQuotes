<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>
    <new-quote @addingQuote="newQuote"></new-quote>
    <app-quote-grid
      v-bind:quotes="quotes"
      v-on:quoteDeleted="deleteQuote"
    ></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-success">
          Info: Click on a Quote to delete it!
        </div>
      </div>
    </div>
  </div>
</template>

<script>
//
import Grid from "./components/Grid.vue";
import NewQuote from "./components/NewQuote.vue";
import Header from "./components/Header.vue";

export default {
  data: function() {
    return {
      quotes: [
        "La poesía es un arma cargada de futuro. La micropoesía es un arma cargada de pasado imperfecto. (Muy imperfecto).",
        "Te adoraré siempre y me importas un pimiento. Todavía no riman, pero ya rimarán con el tiempo.",
        "Compré apio en la frutería (opio no tenían) tuve que tomarme un pepito de ternera (de ternura no quedaban ya). Ahora busco mojama sin parar porque dicen que sabe a-mar.",
        "Compromiso: primera persona del singular del presente de indicativo del verbo comprar miso."
      ],
      maxQuotes: 5
    };
  },
  methods: {
    newQuote(quote) {
      if (this.quotes.length >= this.maxQuotes) {
        return alert("Please delete some Quotes first!");
      }
      this.quotes.push(quote);
    },
    deleteQuote(index) {
      this.quotes.splice(index, 1);
      console.log(index);
    }
  },
  components: {
    appQuoteGrid: Grid,
    newQuote: NewQuote,
    appHeader: Header
  }
};
</script>

<style>
@import "./css/style.css";
</style>
