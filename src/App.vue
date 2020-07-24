<template>
  <div class="container">
    <app-header :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-header>

    <app-quote-form @onAddQuote="onAddQuote"></app-quote-form>
    <app-quote-grid
      :quotes="quotes"
      @onDeleteQuote="onDeleteQuote"
    ></app-quote-grid>

    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">
          Click on a quote to delete it
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Header from "./components/Header.vue";
import QuoteForm from "./components/QuoteForm.vue";
import QuoteGrid from "./components/QuoteGrid.vue";

export default {
  data: function() {
    return {
      quotes: [],
      maxQuotes: 10
    };
  },
  components: {
    appHeader: Header,
    appQuoteForm: QuoteForm,
    appQuoteGrid: QuoteGrid
  },
  methods: {
    onAddQuote(quote) {
      if (this.quotes.length >= this.maxQuotes)
        return alert("Max number of quotes is 10 per user");

      this.quotes.push(quote);
    },
    onDeleteQuote(i) {
      this.quotes.splice(i, 1);
    }
  }
};
</script>

<style></style>
