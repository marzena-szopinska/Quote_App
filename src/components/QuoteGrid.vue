<template>
  <div class="row">
    <!-- render as many quotes as there are in the array -->
    <quote-app v-for="(quote, index) in quotes" :key="quote" v-on:click.native="deleteQuote(index)">
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
  },
  methods: {
    deleteQuote(index) {
      this.$emit("quoteToDelete", index);
    }
  }
};
</script>

<style scoped>
</style>