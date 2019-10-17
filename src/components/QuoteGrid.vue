<template>
  <div class="row">
    <!-- render as many quotes as there are in the array -->
    <quote-app v-for="quote in quotes" v-bind:currentQuote="quote" :key="quote">
      <!-- pass the text as slot -->
      <p>{{ quote }}</p>
    </quote-app>
  </div>
</template>

<script>
import Quote from "./Quote";

export default {
  props: {
    quotes: Array
  },
  components: {
    quoteApp: Quote
  }
};
</script>

<style scoped>
</style>