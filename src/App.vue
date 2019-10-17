<template>
  <div class="container">
    <!-- pass the array of quotes to quote grid component, this components is responsible for rendering each quote that exists -->
    <quote-grid v-bind:quotes="quotes"></quote-grid>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid";

export default {
  data: function() {
    return {
      // keep track of number of quotes
      maxNumOfQuotes: 10,
      // array of quotes
      quotes: ["First Quote"]
    };
  },
  components: {
    // local set up for components
    quoteGrid: QuoteGrid
  }
};
</script>

<style>
</style>
