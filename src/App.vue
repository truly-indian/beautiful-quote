<template>
    <div class="container">
        <app-header :quoteCount="quotes.length" :maxQuotes="10"></app-header>
        <new-quote @quoteAdded='newQuoteAdded'></new-quote>
     <quote-grid :quotes='quotes' @quoteDeleted='deleteQuote'></quote-grid>
     <div class="roq">
<div class="col-sm-12 text-center">
 <div class="alert alert-info">
Info:click on a quote to delete
 </div>
</div>
     </div>
    </div>
   
</template>

<script>
import quoteGrid from './components/quoteGrid.vue'
import newQuote from './components/newQuote.vue'
import header from './components/header.vue'
    export default {
        data: function () {
            return {
                quotes: ['Default quote!!'],
                maxQuotes: 10
            }
        },
        methods:{
            newQuoteAdded(quote) {
                if(this.quotes.length >=this.maxQuotes) {
                    alert('please delete some quotes first !!!')
                }
                else 
                   this.quotes.push(quote)
            },
            deleteQuote(index) {
                this.quotes.splice(index,1)
            }
        },
        components: {
            quoteGrid:quoteGrid,
            newQuote:newQuote,
            appHeader:header
        }
    }
</script>

<style>
</style>
