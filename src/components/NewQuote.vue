<template>
  <div class="row">
    <form>
      <div
        class="form-group col-lg-12 col-sm-8 col-sm-offset-2 col-xs-12 col-md-12 col-md-offset-3"
      >
        <label for="quote">Quote</label>
        <textarea
          class="form-control"
          rows="3"
          v-model="quote"
          id="quote"
        ></textarea>
      </div>
      <div
        class="col-lg-12 col-sm-8 col-sm-offset-2 col-xs-12 col-md-12 col-md-offset-3 form-group"
      >
        <button
          class="btn btn-primary btn-lg btn-block"
          @click.prevent="createNew"
          :disabled="!quote"
        >
          Add Quote
        </button>
      </div>
    </form>
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
    createNew() {
      this.$emit("quoteAdded", this.quote);
      this.quote = "";
    }
  }
};
</script>

<style></style>
