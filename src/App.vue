<template>
  <div class="container">
    <header-app v-bind:quoteCount="quotes.length" v-bind:maxQuotes="maxNumOfQuotes"></header-app>
    <new-quote v-on:newQuoteCreated="quotes.push($event)"></new-quote>
    <!-- pass the array of quotes to quote grid component, this components is responsible for rendering each quote that exists -->
    <quote-grid v-bind:quotes="quotes" v-on:quoteToDelete="deleteQuote"></quote-grid>
    <div class="row">
      <div class="col-sm-12">
        <div class="alert alert-info">Click on a Quote to delete it</div>
      </div>
    </div>
  </div>
</template>

<script>
import QuoteGrid from "./components/QuoteGrid";
import NewQuote from "./components/NewQuote";
import Header from "./components/Header";

export default {
  data: function() {
    return {
      // keep track of number of quotes
      maxNumOfQuotes: 10,
      // array of quotes
      quotes: ["First Quote"]
    };
  }, // or instead v-on:newQuoteCreated="quotes.push($event)" you can simpy to it this way
  methods: {
    newQuote(newQuote) {
      // show a message if the user wants to add more quotes than its allowed
      if (this.quotes.length >= this.maxNumOfQuotes) {
        return alert(
          "Please delete quotes first in order to add different ones"
        );
      }
      // add freshly created quote to quotes array
      this.quotes.push(newQuote);
    },
    deleteQuote(index) {
      // remove element in a position specified in index
      this.quotes.splice(index, 1);
    }
  },
  components: {
    // local set up for components
    quoteGrid: QuoteGrid,
    newQuote: NewQuote,
    headerApp: Header
  }
};
</script>

<style>
</style>
