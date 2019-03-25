<template>
  <div class="container">
    <app-header :maxQuotes="maxQuotes" :quoteCount="quotes.length"></app-header>
    <app-new-quote @quoteAdded="newQuote"></app-new-quote>
    <app-quote-grid :quotes="quotes" @deleteQuote="deleteQuote"></app-quote-grid>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a Quote to delete it!</div>
      </div>
    </div>
  </div>
</template>

<script>
import appQuoteGrid from "./components/QuoteGrid.vue";
import appNewQuote from "./components/NewQuote.vue";
import appHeader from "./components/Header.vue";

export default {
  data() {
    return {
      quotes: ["Just a Quote to see something"],
      maxQuotes: 10
    };
  },
  components: {
    appQuoteGrid,
    appNewQuote,
    appHeader
  },
  methods: {
    deleteQuote(i) {
      this.quotes.splice(i, 1);
    },
    newQuote(q) {
      if (this.quotes.length >= 10) {
        alert("Delete a few quotes first");
        return;
      }
      this.quotes.push(q);
    }
  }
};
</script>

<style>
</style>
