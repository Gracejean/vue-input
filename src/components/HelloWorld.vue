<template>

    <div id="num" >
     <Money v-model="price"></Money>
      <p>Value: {{ price.replaceAll(',', '').split('').join("") }}</p>
      <p>Amount: {{abbrevated}}</p>
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
    },
     created() {
    var a = 10000000;
    var b = ['K', 'M'];
    var numLen = a.toString().length;
    var index = Math.ceil((numLen - 3) / 3);

    if (numLen > 3) {
    console.log(a/Math.pow(1000, index)+ b[index - 1])

    }else{
      console.log(a);
    }

  },
  computed:{
    abbrevated: function(){
      var num = this.price.replaceAll(',', '').split('').join('')
      var b = ['K', 'M'];
      var numLen = num.toString().length;
      var index = Math.ceil((numLen - 3) / 3);

      if (numLen > 3) {
        return num/Math.pow(1000, index)+ b[index-1]

      }else{
        return num
      }

    }
  }

}


</script>

<style scoped>

</style>
