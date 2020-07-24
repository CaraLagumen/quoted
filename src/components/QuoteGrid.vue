<template>
  <div class="row">
    <app-quote
      v-for="(quote, i) in quotes"
      :key="quote"
      @click.native="onDeleteQuote(i)"
      >{{ quote }}</app-quote
    >
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
    onDeleteQuote(i) {
      this.$emit("onDeleteQuote", i);
    }
  }
};
</script>

<style></style>
