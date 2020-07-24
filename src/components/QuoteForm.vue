<template>
  <div class="row">
    <div
      class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group"
    >
      <label>Create a quote</label>
      <textarea class="form-control" rows="3" v-model="quote"></textarea>
    </div>

    <div
      class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3 form-group"
    >
      <button class="btn btn-primary" @click.prevent="onAddQuote">
        Add quote
      </button>
    </div>
  </div>
</template>

<script>
export default {
  data: function() {
    return {
      quote: ""
    };
  },
  methods: {
    onAddQuote() {
      this.$emit("onAddQuote", this.quote);
    }
  }
};
</script>

<style></style>
