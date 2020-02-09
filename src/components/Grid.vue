<template>
  <div class="row">
    <!-- Even though the event happens on the HTML rendered in Quote.vue, we want it to be registered
    here (<app-quote>). That's why we add the "native" modifier -->
    <app-quote v-for="quote in quotes" @click.native="deleteQuote(index)">{{
      quote
    }}</app-quote>
  </div>
</template>

<script>
import Quote from "./Quote.vue";

export default {
  props: ["quotes"],
  components: {
    appQuote: Quote
  },
  methods: {
    deleteQuote(index) {
      this.$emit("quoteDeleted", index);
    }
  }
};
</script>
