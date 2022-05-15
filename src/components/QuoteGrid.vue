<template>
   <div class="row">
       <app-quote-hello v-for="(quote, index) in quotes" :key="quote" @click.native="deleteQuote(index)">{{ quote }}</app-quote-hello>
   </div>
</template>

<script>
   import QuoteHello from './QuoteHello.vue'

   export default {
       props: ['quotes'],
       components: {
           appQuoteHello: QuoteHello,
       },
       methods: {
           deleteQuote(index) {
               this.$emit('deleteQuote', index);
           }
       }
   }
</script>

<style>

</style>
