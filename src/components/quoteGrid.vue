<template>
    <div class="row">
      <appQuote v-for='(Quote,index) in quotes' v-bind:key='Quote' @click.native="deleteQuote(index)">{{Quote}}</appQuote>
    </div>
</template>

<script>
import quote from './quote.vue'
export default {
    props:['quotes'],
    components:{
        appQuote:quote
    },
    methods:{
        deleteQuote (index) {
           this.$emit('quoteDeleted',index)
        }
    }
}
</script>

<style scoped>

</style>