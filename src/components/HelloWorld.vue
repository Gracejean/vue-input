<template>

    <div id="num" >
     <Money v-model="price"></Money>
      <p>Value: {{ price }}</p>
    </div>
</template>

<script>
import Money from './Money.vue'

export default {
  components:{
    Money
  },
  data: function() {
        return {
            price: ''
        }
    }
}


  



</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>

</style>
