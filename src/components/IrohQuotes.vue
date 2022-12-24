<template>
  <div>{{currentQuote}}</div>
</template>

<script>
import quotesData from "../assets/quotes.json";


export default {
  name: 'IrohQuotes',
  props: {
  },
  components: {
    // Quote
  },
  data() {
    return {
      currentQuote: null,
      quotes: quotesData
    }
  },
  methods: {
    getRandomQuote() {
      const d = new Date();
      return this.quotes[(d.getFullYear() * d.getDate() * (d.getMonth() + 1)) % this.quotes.length]['quote'];
    }
  },
  mounted() {
    this.currentQuote = this.getRandomQuote();
  }
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
