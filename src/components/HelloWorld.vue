<template>

    <div id="num" >
     <Money v-model="price"></Money>
      <p>Value: {{ price.replaceAll(',', '').split('').join("") }}</p>
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

<style scoped>

</style>
