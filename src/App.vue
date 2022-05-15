<template>
    <div class="container">
      <app-hea-der-vue :quoteCount="quotes.length" :maxQuotes="maxQuotes"></app-hea-der-vue>
      <app-new-quote-vue @quoteAdded="newQuote"></app-new-quote-vue>
    <app-quote-grid-vue :quotes="quotes" @deleteQuote="deleteQuote"></app-quote-grid-vue>
    <div class="row">
      <div class="col-sm-12 text-center">
        <div class="alert alert-info">Info: Click on a Quote dalete it!</div>
      </div>
    </div>
    </div>
</template>

<script>
   import QuoteGridVue from "./components/QuoteGrid.vue"
   import NewQuoteVue from "./components/NewQuote.vue"
   import HeaDerVue from "./components/HeaDer.vue"

    export default {
        data: function() {
          return {
            quotes: [
                'Just a Quote to see aomething'
            ],
            maxQuotes: 10
          }
        },
        methods: {
          newQuote(Quote) {
            if (this.quotes.length >= this.maxQuotes) {
              return alert('Please delete Quotes first');
            }
            this.quotes.push(Quote);
          },
          deleteQuote(index) {
            this.quotes.splice(index, 1);
          }
        },
        components: {
          appQuoteGridVue: QuoteGridVue,
          appNewQuoteVue: NewQuoteVue,
          appHeaDerVue: HeaDerVue
        }
    }
</script>

<style>
</style>