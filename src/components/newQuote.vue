<template>
    <div class="row">
        <form>
           <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
           <label for="quote">Quote</label>
           <textarea name="quote" class="form-control" rows="3" cols="30" v-model="quote"></textarea>
           <hr>
     </div>
    
      <div class="col-sm-8 col-sm-offset-2 col-xs-12 col-md-6 col-md-offset-3">
           <button class="btn btn-primary" @click.prevent="createNew">Add Quote</button>
           <hr>
     </div>
        </form>
   
    </div>
</template>

<script>

export default {
   data: function () {
       return {
           quote:''
       }
   },
   methods: {
       createNew(event) {
           this.$emit('quoteAdded',this.quote)
           this.quote = ''
       }
   }
}
</script>

<style scoped>

</style>