<template>

    <div  id="num">
     <input v-model="displayValue" v-on:keypress="characters" v-on:keyup="check" />
    </div>
</template>

<script>
export default {
    name:'Money',
    data () {
      return {
        displayValue: null,
      }
    },

   props:["value"],
  methods:{
    check () {
      console.log(this.displayValue);
       if (this.displayValue[0] == 0 && this.displayValue[1]== 0 ){
         this.displayValue = null

   }else{
     this.displayValue = this.displayValue.replace(/^0+/, '').replace(/\D/g, "").replace(/\B(?=(\d{3})+(?!\d))/g, ",")
      this.$emit('input',this.displayValue)

   }
    },

    characters(evt) { 
      
      evt = (evt) ? evt : window.event;
      var charCode = (evt.which) ? evt.which : evt.keyCode;
      console.log(evt);
      if (charCode > 31 &&  charCode > 57 && charCode !== 46 ) {
        evt.preventDefault();
   

   }
       else {
        return true;
      }
    }


  
}
  

}

</script>

<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
