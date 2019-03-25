<template>
  <div class="row">
    <app-quote v-for="(q, i) in quotes" :key="q" @click.native="deleteQuote(i)">{{ q }}</app-quote>
  </div>
</template>

<script>
import appQuote from "./Quote.vue";

export default {
  props: ["quotes"],
  components: {
    appQuote
  },
  methods: {
    deleteQuote(i) {
      this.$emit("deleteQuote", i);
    }
  }
};
</script>

<style scoped>
</style>
